---
icon: material/hand-saw
---

Excellent. These notes are a superb addition and perfectly align with the course's hands-on, business-focused pedagogy. Using personas for a role-playing activity is an outstanding way to achieve your goals:

* **Models Good Practice:** It provides a concrete example of how personas are used to guide product strategy.
* **Focuses Analysis:** It forces students to move beyond a generic reading and adopt a specific, critical lens, making their analysis of the model cards much sharper.
* **Simulates Reality:** The "individual analysis -> team synthesis" flow beautifully mirrors how cross-functional teams work, where legal, product, and finance stakeholders must negotiate trade-offs to reach a decision.
* **Encourages AI Tool Use:** Integrating NotebookLM into the workflow treats it as a professional tool for knowledge synthesis, reinforcing the "AI-assisted learning" approach.

Here is an adaptation of your notes into a structured activity description for the "Juris AI" example, ready to be presented to your students.

---
### **Part 4: 🧠 Learner Activity: The Juris AI Model Showdown**

**Objective:** As a team, analyze competing model cards from the perspective of key business stakeholders to select and justify the foundational LLM for your startup, Juris AI.

**The Scenario:**

You are the founding leadership team of **Juris AI**, a venture-backed startup building a tool to help legal associates summarize complex case law, identify precedents, and draft initial legal briefs. Your success depends on choosing a model that is not only powerful but also safe, reliable, and cost-effective. An incorrect choice could lead to inaccurate legal work, a breach of client confidentiality, or unsustainable operational costs.

**Your Toolkit:**

1.  **Model Cards:** You will be analyzing the model cards for **Gemini 2.5 Pro**, **GPT-5**, and **Claude 4**.
2.  **AI Research Assistant:** All model cards have been loaded into a NotebookLM notebook. You are expected to use the chat feature to query this source material, asking targeted questions to find the evidence you need quickly and efficiently. This simulates how you would work with an AI assistant to synthesize a large volume of technical documentation.

**Activity Structure:**

This is a two-stage activity:
1.  **Individual Deep Dive (15 minutes):** Each team member will adopt one of the personas below. From your persona's perspective, use the NotebookLM to analyze the model cards and form an initial recommendation.
2.  **Team Synthesis & Negotiation (20 minutes):** As a team, each member will advocate for their position based on their persona. Your goal is to negotiate the trade-offs and reach a single, consensus recommendation for Juris AI.

---
#### **Step 1: Adopt Your Persona**

Read your assigned persona description. Use the suggested "Queries for NotebookLM" to begin your investigation.

**Persona 1: Priya Sharma, General Counsel**
* **Your Worldview:** You are the guardian of the company. Your primary concern is mitigating risk. A single lawsuit or data breach could kill the company before it even gets off the ground. You believe a "moat of compliance and safety" is a competitive advantage.
* **What You're Looking For in a Model Card:**
    * **Data Privacy & IP:** Where did the training data come from? What are the policies around user inputs? Is there a risk of our clients' confidential case data being used for training?
    * **Accuracy & Hallucinations:** Legal malpractice is a nightmare scenario. [cite_start]You need the model with the lowest demonstrated hallucination rate, especially on fact-based tasks[cite: 1824, 1925].
    * **Indemnity & Risk:** You want to know about the developer's safety mitigations and policies. [cite_start]How seriously do they take risks like deception or providing disallowed content?[cite: 1937, 1729, 3525]. You're looking for signs of maturity and corporate responsibility.
* **Suggested Queries for NotebookLM:**
    * *"Compare the hallucination rates for GPT-5 and Gemini 2.5 Pro on fact-based benchmarks."*
    * *"Which model card discusses safeguards for protecting user data from being used in training?"*
    * *"Summarize the section on 'Deception' in the GPT-5 system card and the 'Ethical Considerations' in the original Model Cards paper."*

**Persona 2: Ben Carter, Product Manager**
* **Your Worldview:** You live and breathe the user experience. Your goal is to build a product that legal associates *love* because it's fast, smart, and makes their jobs easier. You need to find the model that provides the best capabilities to build killer features, fast.
* **What You're Looking For in a Model Card:**
    * **Core Capabilities:** How well does the model perform on complex reasoning, summarization, and long-document analysis? [cite_start]You're looking for the highest scores on relevant **Evaluation Benchmarks**[cite: 1265, 2701, 3693].
    * **Long Context:** Legal documents are massive. [cite_start]A model with a larger context window (like Gemini 2.5 Pro's 1M tokens) is a huge feature advantage[cite: 1223].
    * **Instruction Following & Steerability:** How well does the model follow complex instructions? [cite_start]A model that is more "steerable" will be easier for your engineers to work with and allow for more sophisticated features[cite: 1789, 4836, 4967].
* **Suggested Queries for NotebookLM:**
    * *"Which model has the largest context window? Cite the specific number."*
    * *"Compare the performance of Claude 4 and Gemini 2.5 Pro on reasoning and factuality benchmarks."*
    * *"Find the section in the Claude 4 system card that discusses reward hacking and instruction-following. How does it compare to its predecessor?"*

**Persona 3: Maria Flores, CEO & P&L Owner**
* **Your Worldview:** You are accountable to the board and your investors. Every dollar counts. While you're excited by the AI vision, you are a pragmatist and a skeptic. You need to see a clear path to ROI and can't afford to bet on unproven hype.
* **What You're Looking For in a Model Card:**
    * [cite_start]**Efficiency & Cost:** Are there architectural details (like Gemini's Mixture-of-Experts) that suggest lower operating costs or faster performance?[cite: 1225]. [cite_start]Is there a smaller, cheaper model variant (`MedLM-medium`, `gpt-5-thinking-mini`) that might be "good enough" for an initial MVP?[cite: 693, 1689].
    * **Proven Capabilities vs. Hype:** You want to cut through the marketing. [cite_start]What do the hard numbers on the **Evaluation** charts actually say?[cite: 533, 1262, 2208]. A 5% improvement might not be worth a 50% increase in cost.
    * **Limitations & Dependencies:** What *can't* the model do? [cite_start]Understanding the **Known Limitations** is crucial for managing stakeholder expectations and planning the product roadmap realistically[cite: 662, 1274].
* **Suggested Queries for NotebookLM:**
    * *"Which models mention a 'Mixture-of-Experts' or MoE architecture? What does that imply for efficiency?"*
    * *"Summarize the 'Known Limitations' for Gemini 2.5 Pro and Imagen 4."*
    * *"Compare the performance of the main GPT-5 model versus its smaller 'mini' version on the Production Benchmarks."*

---
#### **Step 2: Team Synthesis & Final Recommendation**

After your individual analysis, your team must reconvene.
1.  **Advocate:** Each person will briefly present their findings and initial recommendation from their persona's point of view.
2.  **Negotiate:** Using the **Performance, Cost, and Risk** framework, discuss the trade-offs.
    * Priya may argue that Claude 4's detailed safety evaluations make it the least risky choice.
    * Ben might counter that Gemini 2.5 Pro's massive context window is a must-have feature that justifies a slightly less mature safety profile.
    * Maria will challenge both: "Is Gemini's performance uplift worth the potential cost? Is Claude's safety advantage significant enough to overcome its smaller context window?"
3.  **Decide:** Come to a single, consensus recommendation. There is no single "right" answer. The goal is to make a well-reasoned, evidence-based business decision. Your final output should be a single paragraph justifying your choice and explicitly stating the key trade-offs you are willing to accept.

Excellent. Now that we have established the "what," "why," and "how" of analyzing model cards, it's time to apply this knowledge in a practical, simulated business environment. This activity is designed to move you from analyst to decision-maker.

***

### Part 4: 🧠 Learner Activity: The Juris AI Model Showdown

**Objective:** To apply the frameworks and analytical skills from the previous sections in a realistic business scenario. You will work in a team to analyze competing model cards from the perspective of key business stakeholders, negotiate the trade-offs, and make a final, evidence-based recommendation.

#### **The Scenario**

You are the founding leadership team of **Juris AI**, a venture-backed startup building a tool to help legal associates summarize complex case law, identify precedents, and draft initial legal briefs. Your success depends on choosing a foundational model that is not only powerful but also safe, reliable, and cost-effective. An incorrect choice could lead to inaccurate legal work, a breach of client confidentiality, or unsustainable operational costs.

#### **Your Toolkit**

1.  **Model Cards:** You will be analyzing the model cards for **Gemini 2.5 Pro**, **GPT-5**, and **Claude 4**.
2.  **AI Research Assistant:** All model cards have been loaded into a NotebookLM notebook. You are expected to use the chat feature to query this source material, asking targeted questions to find the evidence you need quickly and efficiently. This simulates how you would work with an AI assistant to synthesize a large volume of technical documentation.

---

### **Activity Instructions**

#### **Step 1: Assign Roles**

Your team will be comprised of three key stakeholders. Assign one of the following personas to each team member.

#### **Step 2: Individual Analysis & Roleplay (15-20 minutes)**

Adopt your assigned persona. Use the NotebookLM to analyze the model cards and form an initial recommendation based on your specific priorities and concerns. Use the suggested queries to begin your investigation.

---
**Persona 1: Priya Sharma, General Counsel**

* **Your Worldview:** You are the guardian of the company. Your primary concern is mitigating risk. A single lawsuit or data breach could kill the company before it gets off the ground. You believe a "moat of compliance and safety" is a competitive advantage.
* **What You're Looking For:**
    * [cite_start]**Data Privacy & IP:** Where did the training data come from[cite: 3354]? What are the policies around user inputs? Is there a risk of our clients' confidential case data being used for training?
    * **Accuracy & Hallucinations:** Legal malpractice is a nightmare scenario. [cite_start]You need the model with the lowest demonstrated hallucination rate, especially on fact-based tasks[cite: 613].
    * **Liability & Risk:** You want to know about the developer's safety mitigations and policies. [cite_start]How seriously do they take risks like model **deception** [cite: 718] or providing disallowed content? You're looking for signs of maturity and corporate responsibility.
* **Suggested Queries for NotebookLM:**
    * *"Compare the hallucination rates for GPT-5 and Gemini 2.5 Pro on fact-based benchmarks."*
    * *"Which model card discusses safeguards for protecting user data from being used in training?"*
    * *"Summarize the section on 'Deception' in the GPT-5 system card and the 'Ethical Considerations' in the original Model Cards paper."*

---
**Persona 2: Ben Carter, Product Manager**

* **Your Worldview:** You live and breathe the user experience. Your goal is to build a product that legal associates *love* because it's fast, smart, and makes their jobs easier. You need to find the model with the best capabilities to build killer features, fast.
* **What You're Looking For:**
    * **Core Capabilities:** How well does the model perform on complex reasoning and long-document analysis? [cite_start]You're looking for the highest scores on relevant **Evaluation Benchmarks**[cite: 2226].
    * **Long Context:** Legal documents are massive. [cite_start]A model with a larger context window, like Gemini 2.5 Pro's 1M token window[cite: 2187], is a huge feature advantage.
    * **Instruction Following:** How well does the model follow complex instructions? [cite_start]The Claude 4 system card discusses how improved instruction-following can reduce undesirable behaviors like **reward hacking**[cite: 4640], which means a more reliable user experience.
* **Suggested Queries for NotebookLM:**
    * *"Which model has the largest context window? Cite the specific number."*
    * *"Compare the performance of Claude 4 and Gemini 2.5 Pro on reasoning and factuality benchmarks."*
    * *"Find the section in the Claude 4 system card that discusses reward hacking and instruction-following. How does it compare to its predecessor?"*

---
**Persona 3: Maria Flores, CEO & P&L Owner**

* **Your Worldview:** You are accountable to the board and your investors. Every dollar counts. While you're excited by the AI vision, you are a pragmatist and a skeptic. You need to see a clear path to ROI and can't afford to bet on unproven hype.
* **What You're Looking For:**
    * [cite_start]**Efficiency & Cost:** Are there architectural details (like Gemini's **Mixture-of-Experts** architecture [cite: 2189]) that suggest lower operating costs or faster performance? Is there a smaller, cheaper model variant that might be "good enough" for an MVP?
    * **Proven Capabilities vs. Hype:** You want to cut through the marketing. What do the hard numbers on the **Evaluation** charts actually say? A 5% performance improvement might not be worth a 50% increase in cost.
    * **Limitations:** What *can't* the model do? [cite_start]Understanding the **Known Limitations** [cite: 2238] is crucial for managing stakeholder expectations and planning the product roadmap realistically.
* **Suggested Queries for NotebookLM:**
    * *"Which models mention a 'Mixture-of-Experts' or MoE architecture? What does that imply for efficiency?"*
    * *"Summarize the 'Known Limitations' for Gemini 2.5 Pro and Imagen 4."*
    * *"Compare the performance of the main GPT-5 model versus its smaller 'mini' version on the Production Benchmarks."*

---

#### **Step 3: Team Synthesis & Negotiation (20-25 minutes)**

Reconvene as a team.
1.  **Advocate:** Each member will briefly present their findings and initial recommendation from their persona's point of view.
2.  **Negotiate:** Using the **Performance, Cost, and Risk** framework as your guide, your team must now debate the trade-offs. The General Counsel may argue for the model with the most transparent safety report, while the Product Manager might push for the one with the largest context window. The CEO will challenge both on the cost and ROI implications.

#### **Step 4: Final Recommendation (Your Deliverable)**

Your team must reach a consensus and write a single, concise paragraph (approx. 150-200 words) for your final recommendation. Your justification **must** reference specific evidence from the model cards and explicitly state the key trade-offs your team is willing to accept.