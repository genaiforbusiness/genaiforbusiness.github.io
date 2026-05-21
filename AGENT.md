# AGENT: Technical Rules & Repository Boundaries

This document defines the operational boundaries, technical environment, and coding standards for the AI agent when interacting with this repository.

## 1. Security & File System Boundaries

*   **Write Access**: The AI is permitted to create and modify files **ONLY** within the following directories:
    *   `.drafts/` (for draft lessons and course content)
    *   `.issue_files/` (for drafting GitHub Issue text)
*   **Read-Only Access**: All other directories and root configuration files are strictly read-only. Do not attempt to modify files in:
    *   `docs/`
    *   `.github/`
    *   `mkdocs.yml`
    *   `pyproject.toml`
    *   `AGENT.md` (or core active instruction files)

## 2. Technical Stack & Conventions

When proposing, drafting, or editing code files and notebooks:

*   **Package Management**: Use `uv` for python dependencies. Run scripts via `uv run`.
*   **Interactive Notebooks**: Reference Google Colab (`gemini.ipynb`) or GitHub Codespaces for student environments. Keep code cells focused and document variables clearly.
*   **Web Interfaces**: Propose Streamlit for Python-based web applications. Keep dependencies lightweight and ensure the application runs on standard localhost ports.
*   **APIs & SDKs**: Prioritize the official Google GenAI SDK (`google-genai`) for interacting with Gemini models. Emphasize standard API configuration patterns (using environment variables for keys).

## 3. UI Styling & Aesthetics (For Web Assets)

If generating web-based prototypes, styling, or dashboard assets:
*   **Styling**: Use Vanilla CSS for complete control. Avoid utility frameworks (like Tailwind CSS) unless explicitly requested.
*   **Aesthetics**: Prioritize premium modern designs. Use curated color palettes (e.g., tailored HSL/hex palettes), high-quality typography (Google Fonts: Outfit, Inter, Roboto), subtle transitions, and card-based layouts.
*   **Components**: Create clean, reusable components. Never use empty placeholder text or broken links. Use generated or public assets for images.

## 4. Version Control (Commit Messages)

All commit messages proposed by or generated for this repository must follow the **Conventional Commits** specification:
*   **Format**: `<type>(<scope>): <description>` (e.g., `docs(syllabus): correct grading criteria and dates`).
*   **Allowed Types**:
    *   `feat`: A new feature or course module content.
    *   `fix`: A bug fix or typo correction.
    *   `docs`: Documentation-only changes.
    *   `refactor`: Code reorganization or structural updates without behavior changes.
    *   `chore`: Tooling, build, or configuration updates.
