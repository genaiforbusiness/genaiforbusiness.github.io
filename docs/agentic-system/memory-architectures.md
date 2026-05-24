---
icon: material/memory
---

# Agent Memory Architectures

If Tools are the hands of an autonomous agent, Memory is its brain. A pure LLM is fundamentally stateless—it retains no knowledge of previous interactions between queries. To build an agent capable of executing complex, multi-step workflows, we must design an architecture that provides it with persistent context.

In this lesson, we will explore the different levels of memory architecture, the transition from passive data injection (Traditional RAG) to active retrieval (Agentic RAG), and the physical constraints of context windows.

## Memory Architecture Levels

Agentic memory is not a monolith; it is highly structured. When designing an agent harness, Product Managers must decide what information lives at which level of the system architecture.

### 1. System Memory (The "Core Operating System")
This is the foundational identity and rule set of the agent. It is loaded into the model's context at the very beginning of every session and is immutable during runtime.
*   **Examples:** System Instructions, Persona definitions, and Operational Rules. 
*   **Implementation in Practice:** In repository-level agent harnesses (like the Antigravity CLI), System Memory is often implemented via dedicated markdown files. For example, a `SOUL.md` file might define the agent's persona and tone, while an `AGENT.md` file defines its security boundaries and technical constraints.

### 2. Session Memory (Short-Term State)
This is the "scratchpad" for the current interaction. It maintains the state of a single task or conversation.
*   **Examples:** The chat history of a current conversation, the intermediate steps of a ReAct loop, or a list of files the agent just edited.
*   **Implementation in Practice:** Storing the array of messages in local application memory (RAM) and passing the entire array back to the API with each new request.

### 3. User-Specific / Long-Term Memory
This is persistent knowledge that survives across sessions. It allows an agent to "remember" past interactions with a specific user or access a vast corporate knowledge base.
*   **Examples:** Corporate documents, user preferences, past transaction histories.
*   **Implementation in Practice:** Vector Databases (like Chroma or Pinecone) and standard SQL databases.

## Stateful vs. Stateless Approaches

When building the agent harness, developers must decide how to manage Session Memory:

*   **Stateless Harness:** The LLM API is stateless. In this approach, your application must store the entire history of the conversation and send the complete transcript to the LLM every single time you make a request. This gives developers total control over the context but can quickly consume the token budget and increase latency.
*   **Stateful APIs (Context Caching):** Modern APIs are beginning to offer Context Caching (e.g., Gemini's Context Caching). You can upload a large system prompt or a large document once, and the API maintains that state on its servers for a set duration. Subsequent requests reference that cached context, drastically reducing cost and latency.

## From Traditional RAG to Agentic RAG

To grant an agent Long-Term Memory, we use **Retrieval-Augmented Generation (RAG)**. However, the architectural pattern for RAG changes significantly when moving from a simple chatbot to an autonomous agent.

### Traditional RAG (Passive Injection)
In a standard RAG application, the retrieval happens *before* the LLM is involved. 
1. The user asks a question.
2. The system executes a semantic search against a Vector Database.
3. The system injects the retrieved text into the prompt.
4. The LLM generates an answer.

### Agentic RAG (Active Retrieval)
In an agentic system, retrieval is exposed to the LLM as a **Tool**. The LLM decides *when* to search, *what* to search for, and whether it needs to search multiple times.
1. The user asks a complex question.
2. The LLM agent pauses and uses a `search_database` tool to look up a specific term.
3. The agent reviews the results. If the results are insufficient, it formulates a new search query and uses the tool again.
4. Once it has gathered enough memory, it synthesizes the final answer.

> **Deep Dive: Visualizing Agentic Memory Architecture**
>
> ```mermaid
> graph TD
>     User[User Query] --> Harness[Agent Harness / Orchestrator]
>     
>     subgraph Agent System
>         Harness --> LLM[Reasoning Engine]
>         
>         LLM -- "Reads" --> SystemMem[System Memory: SOUL.md]
>         LLM -- "Updates" --> SessionMem[Session Memory: Chat History]
>         
>         LLM -- "Uses Tool" --> SearchTool[Search Tool]
>     end
>     
>     subgraph Enterprise Infrastructure
>         SearchTool -- "Queries" --> VectorDB[(Vector DB / Chroma)]
>         SearchTool -- "Queries" --> SQL[(Transactional SQL DB)]
>     end
>     
>     VectorDB -. "Returns Context" .-> SearchTool
>     SQL -. "Returns Context" .-> SearchTool
>     SearchTool -. "Injects to LLM" .-> LLM
>     LLM --> Response[Final Action / Response]
> ```

## The Limits of Context: "Lost in the Middle"

With modern models boasting context windows of over 2 million tokens, a common question is: *Why use RAG at all? Why not just put the entire corporate database in the prompt?*

Beyond the exorbitant cost and latency of passing massive prompts, there is a physical limitation in LLM architecture known as the **"Lost in the Middle"** phenomenon. 

Studies show that when LLMs are fed massive amounts of context, they are highly accurate at retrieving information from the very beginning or the very end of the prompt. However, performance degrades significantly when trying to extract specific facts buried in the middle of a massive context window. 

Therefore, even with massive context windows, **Agentic RAG remains essential** for pinpoint accuracy. A targeted search tool that returns the exact paragraph needed will always outperform dumping a 10,000-page manual into the context window.

## Conclusion

Memory is not a single feature; it is a multi-tiered architecture that spans from static markdown files in your repository to dynamic vector databases in the cloud. In the next Builder Session, we will build a Vector Database and expose it to our agent as a tool.

---
## References

Google. (2024). *Context Caching in Gemini API*. Retrieved from https://ai.google.dev/gemini-api/docs/caching
Liu, N. F., Lin, K., Hewitt, J., Paranjape, A., Bevilacqua, M., Petroni, F., & Liang, P. (2024). *Lost in the Middle: How Language Models Use Long Contexts*. Transactions of the Association for Computational Linguistics, 12, 157-173.
