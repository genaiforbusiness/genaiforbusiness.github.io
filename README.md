# Technical Foundations of Generative AI for Business

Welcome to the course repository for *Technical Foundations of Generative AI for Business* (BUSBIS 1530). This repository houses the static documentation site for the course, including the syllabus, lectures, activities, and project guidelines.

---

## AI Instruction System (Agy & IDE Profiles)

To help students build their course projects, this repository offers a modular system of custom instruction files (system prompts) designed to configure AI assistants, CLI agents, or IDE extensions (e.g., Cursor, Antigravity/Agy).

These profiles customize the AI's constraints, tone, and guidance based on **your active project role** and **your current project phase**.

### 1. Core Instruction Files

The base instructions define the global behavior and repository standards. They are split into three modules:
*   **[SOUL.md](file:///.drafts/SOUL.md)**: Establishes the core persona (helpful business professor) and writing style (professional, WSJ/FT-like analytical tone).
*   **[AGENT.md](file:///.drafts/AGENT.md)**: Defines technical standards, directories, and formatting rules (Conventional Commits, secrets management, Streamlit, and Python conventions).
*   **[CONDUCTOR.md](file:///.drafts/CONDUCTOR.md)**: Orchestrates the overall file drafting, issue creation, and verification workflow.

---

### 2. Available Profiles

In addition to the core files, you can layer on specific profile modifiers depending on your context:

#### Role-Based Profiles (Who You Are)
*   **Product Manager ([product-manager.md](file:///.drafts/profiles/roles/product-manager.md))**: Focuses on value propositions, prompt parameters, and the Performance-Cost-Risk triangle. *The AI is restricted from writing raw backend code to ensure you focus on product strategy.*
*   **Software Engineer ([engineer.md](file:///.drafts/profiles/roles/engineer.md))**: Emphasizes system architecture, clean Streamlit state patterns, Google GenAI SDK usage, error boundaries, and dependency management.
*   **Project Manager ([project-manager.md](file:///.drafts/profiles/roles/project-manager.md))**: Focuses on agile task decomposition, repository hygiene, and drafting structured issue templates.

#### Phase-Based Profiles (Where You Are in the Project)
*   **MVP Phase ([mvp.md](file:///.drafts/profiles/phases/mvp.md))**: Focuses on establishing a simple, functional happy path. *The AI will actively discourage feature creep and advanced integrations.*
*   **Refactor Phase ([refactor.md](file:///.drafts/profiles/phases/refactor.md))**: Focuses on prompt optimization, Pydantic structured schemas, API latency, caching, and code modularization.

---

### 3. How to Use

To use these instruction files with an AI assistant or IDE agent:

1.  **Select the Base**: Start with the base files (`SOUL.md` + `AGENT.md` + `CONDUCTOR.md`).
2.  **Compose with Profiles**: Append your active role and phase files. For example, if you are the Technical Lead developing the first prototype, combine:
    ```
    SOUL.md + AGENT.md + CONDUCTOR.md + profiles/roles/engineer.md + profiles/phases/mvp.md
    ```
3.  **Load into AI Runner**: Pass the combined prompt text to your system instructions or place them in your agent configuration (e.g. your `.cursorrules` or system prompt input).
