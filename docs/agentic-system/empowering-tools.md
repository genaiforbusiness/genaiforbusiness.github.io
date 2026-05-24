---
icon: material/tools
---

# Empowering AI with Tools

In our previous session, we established that an AI Agent relies on **Tools** to interact with the real world, retrieve live data, and execute deterministic business rules. 

In this Builder Session, we will move from theory to practice. You will learn how to define a tool, how the LLM understands when to use it, and how to build the code loop that makes "Function Calling" possible.

## The Tool Calling Lifecycle

When you empower an LLM with tools, the interaction model changes from a simple Request/Response to a multi-step lifecycle. 

1.  **User Request & Tool Definition:** You send the user's prompt to the LLM, but you also attach a list of available tools, defined as JSON schemas.
2.  **Model Decision:** The LLM analyzes the prompt. If it determines that it cannot answer the question using its internal knowledge, but *can* use one of your tools, it halts its text generation and returns a **Tool Call Request**.
3.  **Local Execution:** Your application (the harness) receives this request, executes the local Python or Node.js function, and captures the result.
4.  **Result Injection:** Your application sends the function's result back to the LLM.
5.  **Final Response:** The LLM synthesizes the tool's output into a natural language response for the user.

> **Deep Dive: Why JSON Schemas?**
>
> LLMs do not inherently know how to execute Python code. When you provide a "tool" to an LLM, you are actually just giving it a `JSON Schema` that describes the tool's name, its purpose, and the specific parameters it requires. 
> 
> The LLM's job is simply to output a perfectly formatted JSON object that matches your schema. It is entirely up to your application code to parse that JSON, execute the corresponding function, and return the result.

## Hands-On: Defining a Tool

Let's build a practical example. Imagine you are building an AI assistant for an e-commerce platform. You want the assistant to be able to check the real-time inventory of a product. 

First, we define the actual Python function (our business logic):

```python
def check_inventory(product_id: str) -> dict:
    """
    Simulates a database query to check product inventory.
    """
    # In a real app, this would query a SQL database or an API
    inventory_db = {
        "PROD-100": {"name": "Wireless Headphones", "stock": 45, "status": "In Stock"},
        "PROD-200": {"name": "Mechanical Keyboard", "stock": 0, "status": "Out of Stock"}
    }
    
    return inventory_db.get(product_id, {"error": "Product not found"})
```

Next, we define the tool for the LLM. Using the Google GenAI SDK, this process is heavily abstracted and simplified for us:

```python
from google import genai
from google.genai import types

# 1. Initialize the client
client = genai.Client()

# 2. Define the tool configuration
# The SDK automatically generates the JSON schema from your Python function's signature and docstring!
tool_config = types.ToolConfig(
    function_declarations=[check_inventory]
)

# 3. Prompt the model
response = client.models.generate_content(
    model='gemini-2.5-pro',
    contents='Can you check if we have any PROD-100 in stock?',
    config=types.GenerateContentConfig(
        tools=[tool_config],
    )
)

print(response.text) 
# Output will dynamically incorporate the result of the function execution.
```

## The Model Context Protocol (MCP)

As enterprises build more agents, managing hundreds of custom tools becomes a scaling nightmare. If every AI app requires custom Python code to talk to Slack, Jira, or a Postgres database, developer velocity grinds to a halt.

Enter the **Model Context Protocol (MCP)**.

MCP is an emerging open standard that standardizes how AI agents connect to data sources and tools. Instead of writing custom integration code for every tool, MCP allows agents to connect to universal "MCP Servers."

If your organization deploys a Postgres MCP Server, any agent on your network (whether built on Gemini, Claude, or OpenAI) can instantly discover and utilize the database querying tools exposed by that server, assuming it has the correct identity and permissions.

**The PM Perspective:** MCP shifts the focus from building point-to-point API integrations to managing an ecosystem of standardized agent capabilities. When scoping your MVP, look for existing MCP servers for your data sources to drastically reduce your development time.

## Conclusion

By mastering tool calling, you have unlocked the ability to bridge the gap between general AI reasoning and specific, deterministic business logic. In our next sessions, we will explore a very specific and powerful type of tool: **Memory Systems** and **Retrieval-Augmented Generation (RAG)**.

---
## References

Anthropic. (2024). *Introduction to the Model Context Protocol*. Retrieved from https://modelcontextprotocol.io/
Google. (2024). *Gemini API: Function Calling Documentation*. Retrieved from https://ai.google.dev/docs/function_calling
