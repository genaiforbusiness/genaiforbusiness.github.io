---
icon: material/numeric-6
---


## Competitive Teardown of NotebookLM

**Activity Type:** Independent, Asynchronous Analysis

### **Objective**

This activity is designed to bridge the gap between the theoretical concepts of embedding models and their real-world application in a cutting-edge AI product. Upon completion, you will be able to:

* Deconstruct a product's feature set to identify the underlying AI capabilities.
* Map specific product features to the MTEB task categories that power them.
* Articulate the business impact of embedding model performance on user experience and product value.
* Formulate a strategic, technology-informed recommendation for a new product feature.

### **Context & Scenario**

Imagine you are a new Product Manager at a company developing an AI-powered research assistant designed to compete with major players like Google's NotebookLM. Your first task is to conduct a **"competitive teardown"** of NotebookLM to understand its core technology, identify its strengths, and pinpoint potential opportunities for your own product.

Your analysis will focus specifically on the features powered by embedding models. The goal is to prepare a concise brief for your leadership team that explains *how* NotebookLM works at a conceptual level and *what* it implies for your product strategy. You have already been provided with access to a sample notebook to facilitate your research.

### **Core Task & Instructions**

Your primary task is to analyze NotebookLM's features by completing the **Competitive Teardown Template** below. Follow these steps:

1.  **Familiarize Yourself:** Spend some time using the [provided sample NotebookLM notebook](https://notebooklm.google.com/notebook/3a2d406b-9fbe-4e68-91b4-62510ca50433). Interact with its features, create your own notebook, upload a document or two of your own, and pay close attention to how the tool helps you summarize, question, and connect ideas within your source materials.
2.  **Identify Key Features:** Identify 3-4 distinct, embedding-powered features within NotebookLM. Examples include "Source Suggestions," "Document Q&A," the automatically generated "Notebook Guide," "Table of Contents," etc.
3.  **Complete the Template:** For each feature you identify, fill out a row in the "Competitive Teardown Template." Your analysis should be based on the concepts we covered in the "Embedding Models" module.
4.  **Formulate a Strategic Recommendation:** After completing your teardown, answer the final strategic question to propose a new, innovative feature.


### **Competitive Teardown Template**

| NotebookLM Feature | Primary MTEB Task | Supporting MTEB Tasks | Impact of a More Performant Embedding Model |
| :--- | :--- | :--- | :--- |
| **_Example 1: Source Suggestions_** | **Retrieval** | Reranking, STS (Semantic Textual Similarity) | A more performant model would result in more relevant and precise source suggestions. It could better distinguish nuance, reduce the noise of vaguely related sources, and ultimately build greater user trust in the AI's recommendations. |
| **_Example 2: Document Q&A_** | **Retrieval** | Reranking, Summarization | A state-of-the-art model would minimize "Context Rot" by retrieving only the most salient passages. This would enable more accurate, concise answers and, most importantly, allow for highly precise **citations**, which is a critical trust-builder for a research tool. |
| **(Your analysis of Feature 1)** | | | |
| **(Your analysis of Feature 2)** | | | |
| **(Your analysis of Feature 3)** | | | |


### **Strategic Recommendation Prompt**

Based on your analysis of NotebookLM and your understanding of embedding model capabilities, answer the following question in 2-3 paragraphs:

!!! question "Impact of a More Performant Embedding Model"

    **Identify one new, embedding-powered feature that you would recommend for your company's competing product. Which primary MTEB task would this feature rely on, and why would it provide significant, differentiated value to your target users (e.g., students, researchers, analysts)?**


### **Deliverable**

Please submit a single document containing:
1.  Your completed "Competitive Teardown Template" with your analysis of 3-4 features.
2.  Your written response to the "Strategic Recommendation Prompt."

*Submissions will be evaluated on the depth of your analysis, the clear and logical connection you draw between product features and the underlying MTEB tasks, and the strategic rationale for your new feature recommendation.*



## **On-Device AI Product Strategy**

**Activity Type:** Independent, Asynchronous Analysis

#### **Objective**

This activity is designed to extend your understanding of embedding models beyond the cloud to the emerging frontier of on-device and edge AI. Upon completion, you will be able to:

* Analyze a state-of-the-art, on-device embedding model and its strategic value.
* Connect technical features (e.g., quantization, model size) to specific business and user benefits (e.g., privacy, offline access).
* Formulate a product pitch for a new, on-device AI feature.

#### **Context & Scenario**

As we've discussed, most large-scale AI processing happens in the cloud. However, a new wave of highly efficient, powerful models are making it possible to run sophisticated AI directly on user hardware (e.g., smartphones, laptops). This shift from cloud-first to **on-device AI** creates significant new product opportunities and changes the strategic landscape.

<figure markdown="span">
  [![Introducing EmbeddingGemma: The Best-in-Class Open Model for On-Device Embeddings](http://img.youtube.com/vi/Xu1X-J-r5Xk/0.jpg)](https://www.youtube.com/watch?v=Xu1X-J-r5Xk)
  <figcaption>Video: Introducing EmbeddingGemma: The Best-in-Class Open Model for On-Device Embeddings</figcaption>
</figure>


Your task is to watch the [official Google for Developers video on "Embedding Gemma"](https://www.youtube.com/watch?v=Xu1X-J-r5Xk) and then act as a Product Strategist. You will analyze the business implications of this technology and propose a new product feature that leverages its unique strengths.

#### **Core Task & Instructions**

1.  **Watch the Video:** Watch the 4-minute video on Embedding Gemma, paying close attention to the features of the model and the benefits they provide.
2.  **Analyze the Value Proposition:** Complete the "On-Device Value Proposition Canvas" below. This canvas will help you deconstruct the video's content and map the technology's features to concrete business and user value.
3.  **Develop a Product Pitch:** Based on your analysis, develop a concise pitch for a new on-device AI feature for an existing product (e.g., a mobile app for e-commerce, a project management tool, a social media platform).


### **On-Device Value Proposition Canvas**

| Technical Feature | Direct Capability | Business / User Benefit |
| :--- | :--- | :--- |
| **_Example: Small Footprint (Quantization)_** | Runs with low RAM (e.g., 300 MB). | Enables AI on a wider range of older or less powerful devices, expanding the total addressable market. |
| **_Example: On-Device Processing_** | Embeddings are created and stored locally. | **Data Privacy & Security:** Sensitive user data (e.g., private notes, browsing history) never leaves the device, which is a major trust-builder and competitive differentiator. |
| **(Your analysis of MRL / Customizable Dimensions)** | | |
| **(Your analysis of Offline Functionality)** | | |
| **(Your analysis of Multilingual Support)** | | |


### **Product Pitch Prompt**

Based on your analysis, develop a pitch for a new, on-device AI feature. Your pitch should be no more than 3 paragraphs and must answer the following questions:

1.  **What is the product and the new feature?** (e.g., "For the Slack mobile app, we propose a new 'Smart Summary' feature...")
2.  **How does the feature work conceptually?** (e.g., "...that runs on-device to embed a user's recent private messages and channel history.")
3.  **What is the core business/user benefit, made possible by on-device AI?** (e.g., "The key benefit is that users can get instant, personalized summaries of their unread messages without any of their private company data ever being sent to the cloud. This provides offline access and addresses the major security and privacy concerns that prevent many corporations from adopting cloud-based AI tools.")


#### **Deliverable**

Please submit a single document containing:

1.  Your completed "On-Device Value Proposition Canvas."
2.  Your written response to the "Product Pitch Prompt."