---
# icon: material/hand-saw
icon: material/numeric-4
---

## :material-numeric-1-circle: Assign Roles

Your team will be comprised of three key stakeholders. Assign one of the following personas to each team member.

## :material-numeric-2-circle: Individual Analysis & Roleplay

Adopt your assigned persona. Access the provided [public notebook](https://notebooklm.google.com/notebook/3a2d406b-9fbe-4e68-91b4-62510ca50433){:target="_blank"}. Use it to analyze the model cards and form an initial recommendation based on your specific priorities and concerns. Use the suggested queries to begin your investigation.

??? info "Want to create your own notebook from scratch?"

    You can access a copy of all model cards from this [Google Drive directory](https://drive.google.com/drive/folders/1uUt4WQ1-j3dxFTndsYdAeu5tiELy_o6M?usp=drive_link).

### Persona Descriptions

=== "General Counsel"
    **Persona 1: Priya Sharma**

    **Your Worldview:** You are the guardian of the company. Your primary concern is mitigating risk. A single lawsuit or data breach could kill the company before it gets off the ground. You believe a "moat of compliance and safety" is a competitive advantage.

    **What You're Looking For:**

    * **Data Privacy & IP:** Where did the training data come from? What are the policies around user inputs? Is there a risk of our clients' confidential case data being used for training?
    * **Accuracy & Hallucinations:** Legal malpractice is a nightmare scenario. You need the model with the lowest demonstrated hallucination rate, especially on fact-based tasks.
    * **Liability & Risk:** You want to know about the developer's safety mitigations and policies. How seriously do they take risks like model **deception**  or providing disallowed content? You're looking for signs of maturity and corporate responsibility.

    **Suggested Queries for NotebookLM:**

    * *"Compare the hallucination rates for GPT-5 and Gemini 2.5 Pro on fact-based benchmarks."*
    * *"Which model card discusses safeguards for protecting user data from being used in training?"*
    * *"Summarize the section on 'Deception' in the GPT-5 system card and the 'Ethical Considerations' in the original Model Cards paper."*

=== "Product Manager"
    **Persona 2: Ben Carter**

    * **Your Worldview:** You live and breathe the user experience. Your goal is to build a product that legal associates *love* because it's fast, smart, and makes their jobs easier. You need to find the model with the best capabilities to build killer features, fast.
    * **What You're Looking For:**
        * **Core Capabilities:** How well does the model perform on complex reasoning and long-document analysis? You're looking for the highest scores on relevant **Evaluation Benchmarks**.
        * **Long Context:** Legal documents are massive. A model with a larger context window, like Gemini 2.5 Pro's 1M token window, is a huge feature advantage.
        * **Instruction Following:** How well does the model follow complex instructions? The Claude 4 system card discusses how improved instruction-following can reduce undesirable behaviors like **reward hacking**, which means a more reliable user experience.
    * **Suggested Queries for NotebookLM:**
        * *"Which model has the largest context window? Cite the specific number."*
        * *"Compare the performance of Claude 4 and Gemini 2.5 Pro on reasoning and factuality benchmarks."*
        * *"Find the section in the Claude 4 system card that discusses reward hacking and instruction-following. How does it compare to its predecessor?"*

=== "CEO + P&L Owner"
    **Persona 3: Maria Flores**

    * **Your Worldview:** You are accountable to the board and your investors. Every dollar counts. While you're excited by the AI vision, you are a pragmatist and a skeptic. You need to see a clear path to ROI and can't afford to bet on unproven hype.
    * **What You're Looking For:**
        * **Efficiency & Cost:** Are there architectural details (like Gemini's **Mixture-of-Experts** architecture ) that suggest lower operating costs or faster performance? Is there a smaller, cheaper model variant that might be "good enough" for an MVP?
        * **Proven Capabilities vs. Hype:** You want to cut through the marketing. What do the hard numbers on the **Evaluation** charts actually say? A 5% performance improvement might not be worth a 50% increase in cost.
        * **Limitations:** What *can't* the model do? Understanding the **Known Limitations**  is crucial for managing stakeholder expectations and planning the product roadmap realistically.

    * **Suggested Queries for NotebookLM:**

        * *"Which models mention a 'Mixture-of-Experts' or MoE architecture? What does that imply for efficiency?"*
        * *"Summarize the 'Known Limitations' for Gemini 2.5 Pro and Imagen 4."*
        * *"Compare the performance of the main GPT-5 model versus its smaller 'mini' version on the Production Benchmarks."*

---

## :material-numeric-3-circle: Team Synthesis & Negotiation

Reconvene as a team.

1.  **Advocate:** Each member will briefly present their findings and initial recommendation from their persona's point of view.
2.  **Negotiate:** Using the **Performance, Cost, and Risk** framework as your guide, your team must now debate the trade-offs. The General Counsel may argue for the model with the most transparent safety report, while the Product Manager might push for the one with the largest context window. The CEO will challenge both on the cost and ROI implications.

## :material-numeric-4-circle: Final Recommendation

Your team must reach a consensus and write a single, concise paragraph (approx. 150-200 words) for your final recommendation. Your justification **must** reference specific evidence from the model cards and explicitly state the key trade-offs your team is willing to accept.