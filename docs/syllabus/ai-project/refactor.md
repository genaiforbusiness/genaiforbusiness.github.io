---
icon: material/test-tube
---


##  The Experimentation & Refactoring Report

### Objective 🎯

The goal of this project phase is to move your application from a "working prototype" to a "quality prototype." This is not about adding a long list of new features. Instead, the focus is on **experimentation, evaluation, and refactoring**.

Your mission is to systematically test and improve your MVP. You will experiment with different prompt design strategies, evaluate the quality of your chatbot's responses, and refactor your code to make it more efficient and maintainable. This iterative process of improvement is a core part of professional AI development.

### Due Date & Evaluation

* **Due:** See Canvas.
* **Evaluation:** This deliverable is a major component of your **Group Project** grade. The evaluation is structured to reward both solid, methodical improvement and the implementation of advanced capabilities.

    * **Core Requirements (Proficient / "B" Grade):** To pass this stage, all teams must submit a high-quality `EXPERIMENT_LOG.md` that demonstrates a thoughtful process of evaluation and refactoring of their MVP.
    * **Advanced Path (Exemplary / "A" Grade):** To earn the highest marks, teams must complete the core requirements *and* successfully implement one of the optional advanced features (e.g., RAG, Context Caching, or a basic Agent with tools).

---

## Components of the Deliverable

### 1. The Refactored Application Code

* **Requirement:** Your team's GitHub repository should contain the improved version of your application code. The code should be cleaner, better organized, and more robust than your initial MVP.

### 2. The Experiment Log

**`EXPERIMENT_LOG.md`** 

This is the central document for this phase. Create a new file named `EXPERIMENT_LOG.md`. In it, your team must document at least **three** distinct experiments you ran to improve your application.

#### **The Branching Workflow**

For each experiment, you are required to use a separate Git branch to isolate your work. This is standard professional practice and allows you to experiment safely without breaking your main application.

!!! info "Branching Workflow"

    1.  **Create a New Branch:** Before you start, create and switch to a new branch with a descriptive name.
    ```bash
    git checkout -b experiment/new-prompt-design
    ```
    1.  **Run Your Experiment:** Make all your code changes and commits on this new branch.
    1.  **Evaluate & Decide:** Test your changes. If the experiment is successful and you want to keep it, merge it back into your `main` branch.
    ```bash
    git checkout main
    git merge experiment/new-prompt-design
    ```
    If the experiment is unsuccessful, you can simply abandon the branch by switching back to `main`.

#### **Log Template**

Use the following template in your `EXPERIMENT_LOG.md` for each of the three experiments:

```markdown
---
### Experiment #[1]: [A short, descriptive title for the experiment]

* **Git Branch:** `[Name of the branch used for this experiment, e.g., experiment/new-prompt-design]`

* **Hypothesis:** What were you trying to improve, and what change did you think would work? (e.g., "We hypothesized that using a Chain-of-Thought prompt would improve the accuracy of our chatbot's math calculations.")

* **Method:** What specific change did you make on this branch? (e.g., "We replaced our simple question prompt with a new prompt that included the phrase 'Let's think step by step'.")

* **Evaluation:** How did you measure the result? Was the new output better, worse, or the same? Provide examples of the "before" and "after" outputs.

* **Decision:** Did you merge this branch into `main`? Why or why not?
---
```

### **3. (Optional for "A" Grade) Advanced Feature Implementation**

* **Requirement:** If your team is pursuing the "Advanced Path," your application code must include a functional implementation of one of the following:
    * **Retrieval-Augmented Generation (RAG):** The ability to answer questions from a specific document.
    * **Context Caching:** A mechanism to intelligently store and reuse previous results to improve speed or cost.
    * **Basic Agent:** The ability for your application to use a simple external tool (e.g., a calculator or a simple API).
* **Documentation:** Your `EXPERIMENT_LOG.md` should include the implementation of this feature as one of your documented "experiments."
