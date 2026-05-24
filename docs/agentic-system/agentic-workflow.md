---
icon: material/code-brackets
---

# Building an Orchestrated Workflow

In our final Builder Session, we will synthesize everything we have learned—Tools, Memory, and Orchestration—into a cohesive codebase. We will build the "Agent Harness."

While production harnesses often utilize complex graph libraries like LangGraph or specialized multi-agent frameworks like AutoGen, it is crucial to understand the foundational logic of the orchestration loop. We will build a native Python loop that handles tool execution, context management, and error handling.

## The Agent Loop

The core of any agent is the `while` loop that handles the back-and-forth conversation between the LLM (requesting tools) and the Python runtime (executing tools).

```python
from google import genai
from google.genai import types

# 1. Initialize Client and Tools
client = genai.Client()
# Assume `search_database` and `get_weather` are defined Python functions
tool_config = types.ToolConfig(function_declarations=[search_database, get_weather])

def run_agent(user_prompt: str):
    # 2. Initialize Session Memory
    # We must maintain the conversation history to pass back to the stateless API
    conversation_history = [
        types.Content(role="user", parts=[types.Part.from_text(user_prompt)])
    ]
    
    # 3. The Orchestration Loop
    max_steps = 5 # Guardrail: Prevent infinite ReAct loops
    
    for step in range(max_steps):
        # Call the LLM with the entire history
        response = client.models.generate_content(
            model='gemini-2.5-pro',
            contents=conversation_history,
            config=types.GenerateContentConfig(tools=[tool_config])
        )
        
        # Append the LLM's response to history
        conversation_history.append(response.candidates[0].content)
        
        # 4. Check for Tool Calls
        if response.function_calls:
            for tool_call in response.function_calls:
                # 5. Execute the Tool (The Harness action)
                tool_name = tool_call.name
                tool_args = tool_call.args
                
                print(f"Agent requested tool: {tool_name} with args: {tool_args}")
                
                try:
                    # Route to the correct Python function
                    if tool_name == "search_database":
                        result = search_database(**tool_args)
                    elif tool_name == "get_weather":
                        result = get_weather(**tool_args)
                    else:
                        result = {"error": "Unknown tool"}
                        
                except Exception as e:
                    # Graceful Degradation: Never let a Python error crash the agent
                    result = {"error": str(e)}
                
                # 6. Append the Tool Result back to the history
                tool_result_part = types.Part.from_function_response(
                    name=tool_name,
                    response=result
                )
                conversation_history.append(
                    types.Content(role="user", parts=[tool_result_part])
                )
            
            # The loop continues, sending the tool results back to the LLM to process
            continue
            
        else:
            # If no tools were called, the agent has provided a final text answer.
            print("Final Answer:", response.text)
            break
            
    else:
        print("Agent terminated: Exceeded maximum steps.")

# Run the agent
run_agent("What is the weather in New York, and what does the corporate policy say about remote work?")
```

## Optimizing the Loop: Context Caching

Notice that in our `run_agent` loop, the `conversation_history` array grows with every iteration. If the agent executes a database query that returns 50,000 tokens of text, those 50,000 tokens are appended to the history and re-sent to the LLM on the *next* loop iteration. 

This is the primary driver of cost and latency in agentic systems. 

To mitigate this, production harnesses heavily utilize **Context Caching**. By caching the system prompt, the tool definitions, and large document retrievals on the API server, the agent loop only pays the cost of transmitting and processing the *new* tokens (the latest tool call or observation) in each step. 

## 💡 Project Takeaways: Finalizing the Launch Kit

As you wrap up this module and move toward your final **Launch Kit** deliverable, your team must define its Agent Architecture.

1.  **Define Your Tools:** What specific APIs or databases does your MVP need to touch? Write the Python functions and JSON schemas for these tools.
2.  **Design Your Harness:** Will you use a simple Python loop like the one above, or will you adopt a structured framework to enforce a DAG workflow?
3.  **Implement Guardrails:** Ensure your loop has a `max_steps` limit to prevent runaway costs, and wrap all tool executions in `try/except` blocks to ensure graceful degradation when external APIs fail.

By successfully architecting this harness, you transition your project from a static generative prototype into a dynamic, autonomous business solution.

---
## References

Google. (2024). *Gemini API: Function Calling Documentation*. Retrieved from https://ai.google.dev/docs/function_calling
Harrison, C. (2023). *Agentic Systems and Security Boundaries*. Journal of Enterprise AI Architecture, 14(2), 45-62.
