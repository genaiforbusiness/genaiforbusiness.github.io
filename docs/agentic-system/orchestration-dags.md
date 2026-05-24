---
icon: material/graph
---

# Workflow Orchestration: ReAct vs. DAGs

We now have the components of an agentic system: the LLM (reasoning), Tools (hands), and Memory (brain). The final architectural question is **Orchestration**: How do we sequence these components to achieve a complex, long-horizon goal safely and reliably?

In this lesson, we will explore the architectural debate between emergent, "loopy" reasoning (the ReAct pattern) and highly structured workflows (DAGs), and how modern enterprises are adopting Hybrid and Planner-centric approaches.

## The ReAct Pattern: Emergent but "Loopy"

The earliest and most famous orchestration pattern for LLM agents is **ReAct** (Reasoning and Acting). 

In a pure ReAct loop, the orchestration is entirely emergent. The LLM is placed in a `while` loop. It observes the environment, outputs a "Thought" about what to do next, executes an "Action" (tool), receives the "Observation" (tool result), and loops again until it decides it has reached the final answer.

*   **The Advantage:** High flexibility. The agent can handle highly ambiguous, exploratory tasks where the path to the solution is unknown.
*   **The Problem:** Reliability at scale. ReAct agents frequently fall into the **"Local Optimization Trap."** Because they only look one step ahead, they often make a series of locally logical decisions that lead to a global failure. They can get stuck in infinite loops, burning through token budgets without ever completing the task.

## DAG-based Composition & The Planner

Because pure ReAct loops are too unpredictable for strict enterprise compliance, the industry is moving toward **Planner-centric models** using **Directed Acyclic Graphs (DAGs)**.

In this architecture, the workflow is not a blind loop. Instead, the sequence of steps and their dependencies are structured as a graph. 

1.  **The Planner:** When a user request arrives, a highly capable "Planner LLM" analyzes the request and dynamically generates a DAG—a structured step-by-step plan.
2.  **The Execution:** The harness then executes the nodes of the DAG strictly in order.
3.  **The Sub-Agents:** Within each individual node of the DAG, a smaller, specialized agent (or a simple ReAct loop) is spawned to execute that specific, constrained task.

This approach—often formalized as **Agentic Computation Graphs (ACGs)**—combines the reliability and auditability of traditional software engineering with the dynamic adaptability of generative AI.

> **Deep Dive: Fractal Architectures**
>
> If you look closely at the Planner-centric agent architecture, you will notice it perfectly mirrors the underlying architecture of modern LLMs themselves.
>
> In a **Mixture of Experts (MoE)** model architecture, a "Router" parameter network analyzes the incoming token and decides which highly specialized "Expert" subnetwork should process it. 
>
> In a multi-agent system, the "Planner" LLM analyzes the user's prompt and decides which highly specialized "Tools" or "Sub-Agents" should process it. 
>
> This is a **fractal architecture**: the principles of specialized routing and orchestration repeat themselves identically at the micro-level (model weights) and the macro-level (system architecture).

## Conversational Analytics: Agentic DAGs in Action

The shift toward Planner-centric DAGs is most visible in **Conversational Analytics**. 

Modern enterprises want to let users ask complex questions like, *"Why did our margins drop in the West region last quarter?"* A standard RAG system cannot answer this, and a pure ReAct loop would likely crash trying to navigate the massive database schemas.

Instead, a Conversational Analytics system uses a structured Planner to orchestrate the workflow:
1.  **Node 1 (NL2SQL Tool):** Translate the natural language into an SQL query and pull the raw financial data.
2.  **Node 2 (Data Science Agent):** Pass the raw data to a Python tool to calculate the margin variance and identify anomalies.
3.  **Node 3 (Agentic RAG Tool):** Query the document vector database for internal memos regarding the West region to provide qualitative context.
4.  **Node 4 (Synthesizer LLM):** Combine the SQL data, the statistical analysis, and the RAG context into a final, coherent report.

By structuring this as a DAG, the PM ensures that financial data is *always* pulled via SQL, and context is *always* pulled via RAG, enforcing safety and reliability while still leveraging the LLM's dynamic reasoning.

## Conclusion

Orchestration is where AI transitions from a science experiment to a scalable product. By moving beyond simple ReAct loops and adopting Planner-centric DAGs, you can build autonomous systems that are both flexible enough to handle complex queries and reliable enough for enterprise deployment. In our final Builder Session, we will build a robust agent loop.

---
## References

Shinn, N., Cassano, F., Gopinath, A., Narasimhan, K. R., & Yao, S. (2023). *Reflexion: Language Agents with Verbal Reinforcement Learning*. Advances in Neural Information Processing Systems, 36.
Wu, Q., Bansal, G., Zhang, J., Wu, Y., Li, B., Zhu, E., ... & Wang, D. (2023). *AutoGen: Enabling Next-Gen LLM Applications via Multi-Agent Conversation*. arXiv preprint arXiv:2308.08155.
Yao, S., Zhao, J., Yu, D., Du, N., Narasimhan, I., Hwang, V., & Chen, D. (2022). *ReAct: Synergizing Reasoning and Acting in Language Models*. arXiv preprint arXiv:2210.03629.
