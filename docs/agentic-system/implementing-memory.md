---
icon: material/database-search
---

# Implementing Memory & Grounding

In the previous Learner Session, we explored the theoretical architecture of agentic memory. Today, we will roll up our sleeves and build it. 

We will explore two distinct paths for grounding an LLM: utilizing high-level managed services via Google AI Studio, and building a custom Vector Database from scratch using Python and Chroma. Finally, we will address critical enterprise architecture considerations for deploying these systems to production.

## Path A: UI-Driven Grounding (Google AI Studio)

For rapid prototyping and MVP development, Google AI Studio provides managed grounding features. This abstracts away the complexity of managing vector databases and embeddings.

When creating a prompt in AI Studio, you can utilize the **Tools** section to enable **Google Search Grounding**. This acts as an immediate Agentic RAG tool, allowing the model to query live Google Search results to verify facts and reduce hallucinations before generating its response. 

Similarly, you can use the **Files** integration to upload large documents directly into the prompt's context, utilizing the model's massive context window for document-specific grounding.

*This path is ideal for quick validation, but it lacks the fine-grained control required for complex enterprise integrations.*

## Path B: Code-Driven Custom Memory (Python & Chroma)

To build a truly custom, long-term memory system for an agent, we must build a Vector Database. In this exercise, we will use **Chroma**, a popular open-source vector database.

### 1. Ingestion & Embedding
First, we must take our enterprise documents, convert the text into numerical vectors (embeddings), and store them in Chroma.

```python
import chromadb
from chromadb.utils import embedding_functions

# Initialize a local Chroma client
client = chromadb.Client()

# Use a standard embedding model (e.g., all-MiniLM-L6-v2)
sentence_transformer_ef = embedding_functions.SentenceTransformerEmbeddingFunction(model_name="all-MiniLM-L6-v2")

# Create a collection (a "table" in our vector database)
collection = client.create_collection(name="corporate_policies", embedding_function=sentence_transformer_ef)

# Ingest data: We add text chunks, and Chroma automatically generates the embeddings
collection.add(
    documents=["Employees get 20 days of PTO per year.", "The company matches 401k up to 5%."],
    metadatas=[{"source": "HR_Manual"}, {"source": "HR_Manual"}],
    ids=["doc1", "doc2"]
)
```

### 2. Creating the Agentic Tool
Now, we wrap our database query inside a Python function and expose it as a tool, completing the transition to Agentic RAG.

```python
def search_corporate_policies(query: str) -> str:
    """
    Searches the internal HR database for corporate policies.
    """
    results = collection.query(
        query_texts=[query],
        n_results=1 # Return the top 1 most relevant chunk
    )
    
    if results['documents'] and results['documents'][0]:
        return results['documents'][0][0]
    return "No relevant policy found."

# In an agent loop, this function is exposed to the LLM via tool configuration.
```

## 💡 Project Takeaways & Enterprise Architecture

As you integrate memory systems into your course projects (and eventually into enterprise environments), consider the following architectural constraints.

### Transactional vs. Analytical Workloads
Traditional RAG often assumes a static document repository (an analytical workload). However, when building agents that interact with live business operations, you must distinguish between workload types:
*   **Analytical RAG:** Searching through thousands of PDFs or wikis. Vector databases excel here.
*   **Transactional RAG:** Answering questions like "What is the status of order #123?" Vector databases are terrible at this. For transactional workloads, your agent needs an **NL2SQL** tool (Natural Language to SQL) to query the live, relational database directly.

### Enterprise Governance: Security & Access Control
When an LLM agent queries a database on behalf of a user, it must respect enterprise security boundaries.
*   **Row-Level Security (RLS) & Column-Level Security:** If an employee asks the agent "What is the average salary on my team?", the agent's database query tool must execute with the identity of that specific employee. If the employee lacks the database permissions to view salaries (RLS), the database should reject the query, ensuring the agent cannot leak secure data.
*   **Reverse ETL:** To keep vector databases up to date with live business data (e.g., syncing customer support tickets into Chroma), enterprises utilize Reverse ETL pipelines to stream data from Data Warehouses into the Agent's memory systems.

---
## References

Chroma. (2024). *ChromaDB Documentation*. Retrieved from https://docs.trychroma.com/
Google. (2024). *Grounding with Google Search*. Retrieved from https://ai.google.dev/gemini-api/docs/grounding
