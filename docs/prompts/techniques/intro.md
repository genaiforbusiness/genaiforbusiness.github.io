---
icon: material/numeric-1
---

# Introduction to Prompting Techniques


In the previous lesson, we dissected the **Anatomy of a Prompt** and tuned the **Model Configuration** panel. You now have a solid grasp of the fundamental building blocks of any interaction with a Large Language Model (LLM).

But what happens when the problems get more complex?

Imagine you're the Product Manager for a new e-commerce chatbot. A customer types, *"I bought a blue shirt last week, the one like in your summer ad, but it's too small. How do I exchange it for a large?"*

A simple, one-line prompt won't be enough to handle this. How do you design a system of prompts that can reliably understand the user's intent, extract the key details, consult a policy, and generate a helpful, accurate response?

This is where you move from being a prompt user to a **prompt engineer**.


## From Instructions to Recipes 🧑‍🍳

Think of our last lesson as learning about the core ingredients in a kitchen. You know what **Persona**, **Task**, **Context**, and **Format** are, and you know how to control the "heat" with settings like **Temperature**.

Now, it's time to learn the recipes.

Prompting techniques are the proven recipes that combine those basic ingredients to create sophisticated and reliable outputs. Mastering them is the key to solving real-world business problems. [cite_start]It's important to remember that prompt engineering is an **iterative process**[cite: 33, 46]. Your first attempt will rarely be your last. [cite_start]The work involves crafting a prompt, analyzing the model's response, and refining the prompt until you consistently get the high-quality results your product requires[cite: 33, 886].

## Why a Toolkit? 
**The Link Between Task Complexity and Technique 🛠️**

A common question is, "Why do so many prompting techniques exist?" The answer lies in the incredible versatility of modern LLMs. [cite_start]Models like Gemini are **instruction-tuned**, which means they have been specifically trained on vast amounts of data to become exceptionally good at following instructions[cite: 120].

However, not all instructions are created equal.
* A **simple task**, like "Summarize this article," requires a simple, direct instruction.
* A **complex task**, like our chatbot example, requires a more sophisticated instruction to guide the model through a multi-step reasoning process.

The different prompting techniques you are about to learn are simply structured, expert-level ways of giving instructions. Your job as a PM and prompt engineer is to match the complexity of your task to the power of your technique.


## Computational Thinking for Prompts

At its core, prompt engineering is an application of **computational thinking**. You are translating a human-centric business problem into a structured format that a machine can understand and execute. Two key concepts will help you do this effectively: **Decomposition** and **Pattern Recognition**

### Decomposition 

This is the practice of breaking down a large, complex problem into a series of smaller, manageable sub-tasks. For our e-commerce chatbot, you wouldn't ask the LLM to "solve the customer's problem." Instead, you would decompose the task:

1.  **Task 1 (Intent Recognition):** Classify the user's request. Is it a return, an exchange, or a question?
2.  **Task 2 (Entity Extraction):** Identify and extract key pieces of information: `item: "blue shirt"`, `original_size: "small"`, `desired_size: "large"`.
3.  **Task 3 (Response Generation):** Given the intent and entities, generate a helpful response based on the company's exchange policy.

!!! info "Composition: Building It Back Up 🧩"

    Composition is the inverse of decomposition. It's the practice of **building a complex task by assembling a sequence of simpler, well-understood tasks.** When a single, complex prompt fails, it's often more reliable to create a chain of simpler prompts.

    This is where your knowledge of model capabilities on benchmark tasks (like those in MTEB) becomes a superpower. You can design a complex workflow by composing tasks you know the model performs well on.

    **Example: Building an "Automated Customer Feedback Analyzer"**
    Instead of one giant prompt like "Analyze this feedback," you can **compose** the workflow from three MTEB-like tasks:

    1.  **Prompt 1 (Classification):** "Classify the sentiment of the following text as 'Positive', 'Negative', or 'Neutral': *[Customer Feedback]*"
    2.  **Prompt 2 (Summarization):** "Summarize the key point of the classified feedback in one sentence: *[Customer Feedback]*"
    3.  **Prompt 3 (Extraction):** "From the feedback, extract the specific product features mentioned: *[Customer Feedback]*"
    By composing the solution this way, each step is more reliable, and the overall result is more accurate and easier to debug.

### Pattern Recognition

As you build more AI features, you'll notice that most business needs fall into recurring patterns. You'll learn to see a request and immediately think, "Ah, that's a classification task, which calls for a few-shot prompt," or "This requires logical steps, so I should start with a Chain-of-Thought prompt." Recognizing these patterns is what turns prompt design from guesswork into a repeatable, engineering discipline.