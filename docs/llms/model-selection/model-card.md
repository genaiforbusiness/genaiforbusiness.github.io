---
icon: material/card-bulleted-outline
---
# Model Card

## Aligning Model Selection With Business Priorities
**Reading Model Cards**

This session provides the tools to move from AI hype to business reality. As a technology decision maker, your role is not just to adopt new technology, but to scrutinize its claims, manage its risks, and ensure it delivers tangible value. In this part of the course, we focus on the primary tool for this due diligence: the model card.

## What is a Model Card?

!!! success "**The Spec Sheet You Must Demand**"

    An AI model without a model card is a **black box**. It represents an unverified technology with unknown risks and liabilities. A model card is the **minimum standard of evidence** you should demand from any vendor before considering a pilot, let alone a deployment. It is your primary tool for conducting due diligence, verifying vendor claims, and managing the significant financial, legal, and reputational risks of AI.


Before your company signs a multi-million dollar contract for a new software platform, you review the Service Level Agreement. Before acquiring a company, you conduct exhaustive financial and legal due diligence. Adopting a powerful AI model requires the same, if not greater, level of scrutiny.

A **model card** is the essential spec sheet for an AI model. It is a standardized document that discloses a model's performance, assumptions, and limitations in a transparent way, much like a nutrition label on food or a technical manual for machinery.

## Why Model Cards Exist? 
**A Necessary Response to Costly Failures**

For years, the AI industry lacked standardized documentation procedures to communicate the performance characteristics of trained models. This oversight became a serious problem as models were deployed in high-stakes areas like healthcare, employment, and law enforcement, often with serious impacts on people's lives.

Systematic errors and biases were often only exposed *after* a model was in use, causing direct harm to individuals and significant reputational damage to the companies that deployed them. A well-documented example occurred when MIT Media Lab graduate student Joy Buolamwini found that commercial facial recognition systems failed to detect her face, which led to research demonstrating disproportionate error rates on darker-skinned women.

This mirrors lessons learned the hard way in other industries.

* **In Medicine:** For decades, many clinical drug trials excluded women, leading to medications that had unforeseen side effects or improper dosages for female patients. In response, regulators like the U.S. FDA now mandate that trial results be disaggregated by demographic groups like age, race, and gender.
* **In Automotive Safety:** For years, the industry used crash-test dummies based on a prototypical male physique. It was only after researchers discovered that women were more likely to suffer certain serious injuries in side-impact crashes that dummies with female characteristics were introduced.

These examples highlight a fundamental principle of risk management that the AI industry is now adopting: systems must be tested under conditions that reflect the diversity of the real world. To address this critical gap, researchers at Google proposed the "Model Cards for Model Reporting" framework as a step towards responsible and transparent practice.

## Model Due Diligence

A model card is not a marketing document. It is a tool for governance, risk management, and strategic planning. By demanding and analyzing a model card, you shift the conversation from trusting a vendor's sales pitch to verifying their technical claims.

* **Verifying Vendor Claims:** The AI marketplace is filled with bold claims about performance. A model card provides benchmarked evaluation data, allowing you to cut through the hype and see how a model performs under a variety of controlled conditions. It is the beginning of an evidence-based evaluation, forcing a vendor to show, not just tell, how their model works.

* **Managing Liability & Governance:** This is a primary function for your legal and risk teams. A model card's sections on **"Intended Use"** and **"Limitations"** define the vendor's line in the sand for what their technology should and should not be used for. Using a model for a prohibited application could expose your company to significant legal action. Furthermore, disclosures on fairness and bias provide a necessary, though not sufficient, assessment of the potential for discriminatory outcomes that could lead to brand damage and lawsuits.

* **Informing Financial & Strategic Decisions:** By detailing a model's documented capabilities and, more importantly, its **"Known Limitations,"** a model card helps you make more accurate assessments of project timelines, potential failure points, and the true cost of implementation. It helps you decide if a technology is mature enough for your specific business problem or if the investment is premature.

## A Tool for Every Stakeholder

Model cards are designed to serve a wide range of stakeholders, each looking at the document through a different lens:

* **Model Developers** can compare results to other models and make decisions about training their own systems.
* **Software Developers** can inform their design and implementation decisions based on the model's stated performance characteristics.
* **Policymakers** can better understand how a system may fail or succeed in ways that impact people.
* **Organizations** can inform their decisions about adopting technology that incorporates machine learning.
* **Impacted Individuals** who may be affected by a model's decisions can use the information to understand how it works or to pursue remedies.

In essence, demanding and analyzing a model card is the first step in treating AI not as a magical black box, but as a powerful and complex piece of technology that must be rigorously evaluated before it touches your business, your employees, or your customers.

## Check Your Understanding ✅ 

**An AI vendor presents a new model, highlighting its "state-of-the-art" performance but does not provide a model card. From a leadership perspective, what is the most significant immediate risk?**

<ol type="a" markdown>

1. The model might be slightly more expensive than competitors.
1. The marketing team won't know how to promote the new features.
1. There is no verifiable evidence of its performance, safety, or limitations, exposing the company to unknown operational and legal risks.
1. The engineering team might prefer to build a similar model in-house.
</ol>

??? question "Check Your Answer"

    The correct answer is (c).
