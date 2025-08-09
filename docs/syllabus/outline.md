### Module 1: Scoping & Foundation Models

**Week 1**

* **1A: Course Overview & The AI Proof-of-Concept Challenge**
    * **Session Goal:** To understand the course's structure, objectives, and the semester-long project narrative.
    * **Core Concepts:** We'll introduce the "cross-functional team building a PoC for funding" framework. We'll discuss the grading philosophy, the course schedule, and what success looks like.
    * **In-Class Activity:** A guided tour of the course website and tools. We'll end with an open Q&A to ensure everyone is on the same page.
* **1B: The Generative AI Stack: GitHub, Codespaces, & Foundational APIs**
    * **Session Goal:** To get hands-on with the core tools we'll use all semester.
    * **Core Concepts:** Introduction to the key platforms: GitHub for project management, GitHub Codespaces as our cloud-based coding environment, and Google AI Studio for experimenting with foundational models.
    * **In-Class Activity:** A hands-on tutorial where every student accepts their GitHub Codespaces invitation, creates their first repository from a template, and makes their first "commit."

**Week 2**

* **2A: Problem Framing: Identifying High-Value Use Cases for LLMs**
    * **Session Goal:** To learn how to spot opportunities where Generative AI can solve real business problems.
    * **Core Concepts:** We'll discuss frameworks for analyzing business processes to find pain points suitable for AI automation or augmentation. We'll differentiate between "cool tech demos" and "valuable business solutions."
    * **In-Class Activity:** Teams will form and begin brainstorming potential project ideas, using a provided template to evaluate each idea's business value.
* **2B: User-Centric Design: Personas & User Stories for AI**
    * **Session Goal:** To learn how to define your target user and their needs in a structured way.
    * **Core Concepts:** Introduction to creating simple **user personas** (who are you building for?) and writing effective **user stories** (what do they want to achieve?). This ensures your project is focused on solving a human problem.
    * **In-Class Activity:** Each team will select their project idea and draft a primary user persona and at least three core user stories for their application.

**Week 3**

* **3A: AI Project Lifecycle & Task Tokenization**
    * **Session Goal:** To learn how to manage an AI project by breaking down large goals into small, concrete tasks.
    * **Core Concepts:** Introduction to the iterative nature of AI projects (scope -> prototype -> evaluate). We'll cover how to "tokenize" a user story into specific, assignable tasks that can be tracked on a project board.
    * **In-Class Activity:** A workshop where teams convert their user stories from the previous session into actionable issues on their GitHub Project board.
* **3B: Workshop & Deliverable I: Project Scope & User Stories**
    * **Session Goal:** To finalize the initial project plan and get feedback before development begins.
    * **Core Concepts:** This session is a dedicated workshop.
    * **In-Class Activity:** Each team will present their user persona and project board to another team for peer feedback. The instructor will circulate to provide guidance. The final deliverable is due at the end of this session.

***

### Module 2: Prompting & Application Architecture

**Week 4**

* **4A: Application Architecture: Building a UI with Streamlit**
    * **Session Goal:** To learn the basics of building a simple web user interface (UI) for your AI application using Python.
    * **Core Concepts:** We'll introduce **Streamlit**, a library that makes it easy to create interactive UIs. We'll cover basic elements like titles, text inputs, and buttons.
    * **In-Class Activity:** A follow-along coding session where everyone builds a simple "Hello, World!" Streamlit app in their GitHub Codespace.
* **4B: API Integration: The Core Conversation Loop**
    * **Session Goal:** To connect the Streamlit front-end to a backend LLM API, creating a basic, functional chatbot.
    * **Core Concepts:** We'll cover the fundamentals of Application Programming Interfaces (APIs). We'll learn how to send a user's input from the Streamlit UI to the Google Gemini API and display the model's response.
    * **In-Class Activity:** Teams will work on implementing the core conversational logic for their project's MVP.

**Week 5**

* **5A: Prompt Engineering I: Zero-Shot & Few-Shot Prompting**
    * **Session Goal:** To learn the fundamental techniques for instructing and guiding LLMs.
    * **Core Concepts:** We'll define what a **prompt** is and its critical role. We'll explore **zero-shot** prompting (giving a direct instruction) and **few-shot** prompting (providing a few examples to guide the model's output format).
    * **In-Class Activity:** A hands-on lab in Google AI Studio where students experiment with different prompting techniques to solve specific tasks.
* **5B: Prompt Engineering II: Role-Playing, Personas, & Tone**
    * **Session Goal:** To learn how to give your chatbot a consistent and appropriate personality.
    * **Core Concepts:** We'll cover how to use system prompts and role-playing instructions (e.g., "You are a helpful and friendly customer service assistant") to control the model's tone, style, and persona.
    * **In-Class Activity:** Teams will draft and test the "system prompt" that defines the core personality of their project's chatbot.

**Week 6**

* **6A: Responsible AI I: Bias, Fairness, & Hallucination**
    * **Session Goal:** To understand the primary ethical risks associated with generative AI systems.
    * **Core Concepts:** We'll discuss how societal **biases** in training data can lead to unfair or stereotyped outputs. We'll also define **hallucinations** (when the model confidently makes up incorrect information) and discuss why they happen.
    * **In-Class Activity:** A case study analysis of a real-world AI failure, discussing its impact and root causes.
* **6B: Responsible AI II: Safety Filters & Content Moderation**
    * **Session Goal:** To learn about the practical tools and techniques used to make AI systems safer.
    * **Core Concepts:** We'll explore built-in **safety filters** in commercial APIs (like the Gemini API) that block harmful content. We'll also discuss the importance of content moderation and responsible application design.
    * **In-Class Activity:** Teams will brainstorm potential misuses of their own project and discuss what safeguards they could implement.

**Week 7**

* **7A: In-Class Workshop: MVP Debugging & Prompt Tuning**
    * **Session Goal:** To provide dedicated time for teams to solve technical problems and improve their MVP with instructor support.
    * **Core Concepts:** This session is a hands-on workshop. The focus is on practical problem-solving.
    * **In-Class Activity:** Teams work on their projects. The instructor will circulate, acting as a technical consultant to help with code bugs, API issues, and difficult prompts.
* **7B: Peer Feedback Session I**
    * **Session Goal:** To get fresh eyes on your project and provide constructive feedback to another team.
    * **Core Concepts:** Giving and receiving constructive feedback is a critical professional skill.
    * **In-Class Activity:** Each team will do a brief, informal demo of their MVP to another team and receive feedback based on a provided worksheet.

**Week 8**

* **8A: MVP Checkpoint & Code Review**
    * **Session Goal:** To conduct a formal check-in on the project's progress and the quality of the codebase.
    * **Core Concepts:** Introduction to the concept of a **code review**, where developers examine each other's code to improve its quality and find bugs.
    * **In-Class Activity:** The instructor will do a brief, live code review of one or two volunteer projects, highlighting best practices.
* **8B: Deliverable II: MVP Submission**
    * **Session Goal:** To finalize and submit the Minimum Viable Product for grading.
    * **Core Concepts:** This session is a final work period.
    * **In-Class Activity:** Teams use the class time to put the finishing touches on their MVP and submit it via GitHub.

***

### Module 3: Grounding & Model Evaluation

**Week 9**

* **9A: Grounding I: Introduction to Retrieval-Augmented Generation (RAG)**
    * **Session Goal:** To understand how to connect an LLM to your own private data, making it vastly more useful.
    * **Core Concepts:** We'll explain the concept of **grounding**—basing an LLM's answers on verifiable facts. We'll introduce **Retrieval-Augmented Generation (RAG)** as the primary technique for achieving this, involving a vector database and a retrieval mechanism. 
    * **In-Class Activity:** A conceptual walkthrough of a RAG system, tracing how a user's question retrieves a specific document chunk which is then passed to the LLM.
* **9B: Grounding II: Building a Basic RAG Pipeline**
    * **Session Goal:** To get hands-on experience implementing the core components of a RAG system.
    * **Core Concepts:** We'll cover the practical steps: text chunking, creating embeddings, storing them in a simple vector database, and modifying the application logic to perform retrieval before generation.
    * **In-Class Activity:** A guided coding session where students implement a simplified RAG pipeline that can answer questions from a single text document.

**Week 10**

* **10A: Model Evaluation: Reading Model Cards & Performance Metrics**
    * **Session Goal:** To learn how to critically evaluate and compare different AI models for a specific task.
    * **Core Concepts:** We'll introduce **Model Cards**, which are like nutrition labels for AI models, detailing their performance, biases, and intended uses. We will discuss the difference between general capability and performance on a specific, narrow task.
    * **In-Class Activity:** Students will be given a sample business problem and two different model cards, and as a group, they will discuss which model is better suited for the job and why.
* **10B: Human-AI Interaction: Principles of AI UX**
    * **Session Goal:** To learn design principles for creating AI applications that are trustworthy, understandable, and effective.
    * **Core Concepts:** We'll discuss key AI UX principles like setting clear expectations, providing affordances for correction, and indicating when the system is "thinking" or using external data (like with RAG).
    * **In-Class Activity:** Teams will critique their own project's user interface based on the AI UX principles and brainstorm specific improvements.

**Week 11**

* **11A & 11B: == Project Booster: Async Week ==**
    * **Session Goal:** To provide a full week of dedicated, uninterrupted time for teams to work on implementing RAG and refining their projects.
    * **No formal class sessions will be held.** The instructor will be available for consultations during scheduled office hours.

**Week 12**

* **12A: In-Class Workshop: RAG Implementation & UX Refinement**
    * **Session Goal:** To provide hands-on support as teams integrate the more complex features into their projects.
    * **Core Concepts:** This session is a dedicated workshop for practical problem-solving.
    * **In-Class Activity:** Teams work on their projects with the instructor acting as a consultant, helping with RAG implementation, UX improvements, and overall project strategy.
* **12B: Deliverable III: Project Roadmap & Draft Pitch Deck**
    * **Session Goal:** To finalize the project's strategic documents before the final push.
    * **Core Concepts:** This is a final work period for the deliverable.
    * **In-Class Activity:** Teams use the class time to polish their project roadmap and the draft of their final presentation slide deck for submission.

***

### Module 4: Deployment & Demonstration

**Week 13**

* **13A: Stakeholder Communication: Pitching Your PoC**
    * **Session Goal:** To learn how to structure a compelling story and presentation for a business audience.
    * **Core Concepts:** We'll cover the key elements of a successful tech pitch: start with the problem, present your solution and a live demo, articulate the value proposition, and end with a clear "ask" or call to action.
    * **In-Class Activity:** A workshop on presentation design and storytelling. Teams will outline the narrative for their final pitch.
* **13B: Production Readiness: Final Testing & Polishing**
    * **Session Goal:** To shift focus from feature development to stability, polish, and creating a seamless demo experience.
    * **Core Concepts:** We'll discuss the importance of thorough testing, bug fixing, and preparing a "demo script" to ensure the final presentation goes smoothly.
    * **In-Class Activity:** A final, intensive work session for teams to test their applications, fix bugs, and rehearse their live demos.

**Week 14**

* **14A & 14B: == Thanksgiving Recess ==**
    * No class sessions will be held.

**Finals Week**

* **Final Project Presentations & Demonstrations**
    * **Session Goal:** To present your team's proof-of-concept to the "funding committee" (the class and instructor).
    * **Activity:** Each team will deliver their final, timed presentation and live application demo. This is the culmination of the semester's work.