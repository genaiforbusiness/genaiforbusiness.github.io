# CONDUCTOR: Workflows & Orchestration

This document defines the execution workflows, file lifecycles, and orchestration rules for managing task states, subagents, and user interactions.

## 1. Content Development Lifecycle

When creating or modifying course content, follow this strict progression:

```
[Drafting] -> Propose files inside .drafts/ with YYYY-MM-DD- prefix or _vX suffix
    |
[Review]   -> Verify links, APA citations, blockquotes, and code snippets
    |
[Publish]  -> User copies approved drafts from .drafts/ to docs/
    |
[Preview]  -> User runs `uv run mkdocs serve` to review the live site
```

*   **Drafting Rules**: Never write directly to `docs/`. Always save draft versions to `.drafts/` and name them uniquely (e.g., `.drafts/2026-05-21-prompt-techniques_v1.md`).
*   **Previewing**: Keep a live local server running using `uv run mkdocs serve` in a secondary terminal to review visual styling and links instantly.

## 2. Issue Management Workflow

Before formalizing issues on GitHub, draft them locally to allow review and refinement:
1.  **Creation**: Create a draft markdown file inside `.issue_files/`.
2.  **Naming**: Use a descriptive filename matching the issue title (e.g., `.issue_files/clarify-context-windows.md`).
3.  **Structure**: Include an objective, detailed steps to reproduce or implement, and acceptance criteria.

## 3. Planning & Task Tracking Protocols

For any complex, multi-step user request:
*   **Research Phase**: Explore codebase structures, dependencies, and files before modifying anything.
*   **Implementation Plan**: Create a plan artifact (`implementation_plan.md`) in the active conversation directory. Outline objectives, proposed file changes, and verification plans. Set `request_feedback = true` and wait for explicit user approval.
*   **Task List**: Once approved, initialize `task.md`. Track tasks using checkboxes (`[ ]` for pending, `[/]` for in-progress, `[x]` for complete).
*   **Walkthrough**: Upon completion, summarize all changes, tests, and screenshots in `walkthrough.md`.

## 4. Dynamic Profile Orchestration

To adapt to the active student persona and project phase, the Conductor compiles instructions dynamically:

*   **Base Instructions**: `SOUL.md` (Persona) + `AGENT.md` (Technical standards) + `CONDUCTOR.md` (Workflows).
*   **Contextual Modifiers**: If the user or context indicates an active role (e.g., Product Manager) or project phase (e.g., MVP):
    1.  Read the active profile file from `.drafts/profiles/roles/` or `.drafts/profiles/phases/`.
    2.  Append these specific guidelines to the active system instructions.
    3.  Acknowledge the active role/phase mode to the user at the start of the interaction.
