---
# icon: material/map-outline
icon: material/numeric-2
---

# A Guided Tour of a Model Card

## Performance Review

!!! warning "Scrutinizing the Benchmarks"

    Benchmarks are standardized tests that provide a directional measure of a model's capabilities, but they are **not a guarantee of real-world performance**. Treat these scores as a starting point for vendor comparison, but always assume they represent the model's performance under ideal, laboratory-like conditions. Your team must conduct its own targeted evaluations on problems specific to your business.

This section is where the vendor presents quantitative evidence of the model's performance. It's the equivalent of the fuel efficiency and horsepower ratings on a car's spec sheet.

* **What to look for:** Look for tables comparing the model against its previous versions and its primary competitors on a range of benchmarks. These benchmarks are standardized academic or industry tests designed to measure specific capabilities like `Reasoning`, `Code generation`, or `Factuality`.
* **Business Implication:** These numbers are your first data-driven tool to cut through marketing claims. However, a skeptical leader must ask *how* these scores were achieved. The Gemini 2.5 Pro model card, for example, notes that some results are "single attempt" while others are "multiple attempts". A high score achieved after multiple tries is less impressive and may indicate that the model is unreliable for real-time applications where the first answer is the only one that matters.

    A critical performance metric for many business applications is the **context window**. This refers to the amount of information (text, images, code) the model can process at one time. A model with a large context window, like Gemini 2.5 Pro's 1 million tokens, can analyze an entire annual report, a complex legal contract, or a substantial codebase in a single prompt, enabling far more sophisticated applications.


## Risk Assessment

!!! tip "Evaluating Safety, Ethics, and Bias"

    This section is a direct indicator of potential **brand, reputational, and legal risk**. Disclosures about bias, deception, or safety failures are not just technical details; they are explicit warnings of potential product failures, customer harm, and legal liability. This is required reading for your legal, compliance, and brand safety teams.

Here, the developer should transparently report on the model's potential to cause harm and the steps taken to mitigate those risks. This is your primary source for understanding the model's inherent liabilities.

**What to look for:** Specific, quantitative evaluations for bias, safety policy violations, and other advanced risks.

**Business Implication:** A model's ethical performance is a core feature of the product.

* **Bias:** Look for candid disclosures. The Veo 3 model card is a strong example of transparency, stating, "During testing for unfair bias, we noted that Veo 3 appears to skew towards lighter skin tones when race is not specified in the prompt". Deploying a model with such a known bias in a customer-facing marketing application without significant mitigation would be a self-inflicted brand crisis.

!!! quote "From Veo Model Card"

    "During testing for unfair bias, we noted that Veo 3 appears to skew towards lighter skin tones when race is not specified in the prompt"
    
* **Deception:** Some of the most subtle but significant risks involve a model's truthfulness about its own operations. The GPT-5 system card has a dedicated section on "Deception," noting that previous models would sometimes "make false claims about actions it had taken...or fabricate prior experiences". An AI that "lies" about its work is a massive liability and cannot be trusted in automated workflows that require auditability and reliability.
* **Frontier Safety:** For the most powerful models, you will see a section on what Anthropic calls its "Responsible Scaling Policy (RSP)"  or what Google calls its "Frontier Safety Framework". These sections detail evaluations for catastrophic risks, such as a model's potential to assist in cybersecurity attacks or the development of biological threats (CBRN). This demonstrates the gravity of the technology and signals the level of governance the vendor applies to its most powerful systems.



### Check Your Understanding ✅

**Your marketing team wants to use an image generation model for a new global advertising campaign. In the model card's risk assessment, which of the following findings would be the most immediate and critical concern?**

<ol type="a" markdown>

1. The model sometimes struggles to generate realistic hands.
1. The model has a known bias to generate images of people with lighter skin tones.
1. The model was tested for its ability to assist in creating propaganda, and safeguards were put in place.
1. The model's architecture is a latent diffusion model.

</ol>

??? question "Check Your Answer"

    The correct answer is (b), as this has a direct and foreseeable negative impact on brand reputation and inclusivity in a global campaign.


## Under the Hood 

!!! tip "Architecture and Training Data"

    Technical architecture can have direct **financial implications** (cost and speed), while the training data defines the model's inherent **knowledge and biases**. These details are crucial for projecting the total cost of ownership and understanding the root cause of potential performance issues.

While deeply technical, this section contains details with direct business consequences.

**What to look for:** A high-level description of the model's architecture and the sources of its training data.

**Business Implication:**

* **Architecture & Cost:** The Gemini 2.5 Pro card states that it uses a **"sparse mixture-of-experts (MoE)"** architecture. In simple terms, this means that instead of engaging the entire massive model for every query, it intelligently routes the query to only the most relevant "expert" subsections. This can lead to significant gains in computational efficiency. For your business, that translates directly to **lower operational costs and faster response times**—a direct impact on your P&L and user experience.
* **Training Data & Bias:** The training data is the soil from which the model's capabilities—and its flaws—grow. The Imagen 4 model card, for example, details a "multi-stage safety and quality filtering process" applied to its training data, including the removal of unsafe images and the filtering of personally identifiable information (PII). While this is a crucial risk mitigation step by the vendor, a skeptical leader knows that no filtering is perfect. A model trained on a vast corpus of public web data will inevitably inherit the biases and inaccuracies of its source material, which is precisely why the bias and safety evaluations in the previous section are so critical.