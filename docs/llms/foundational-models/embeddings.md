---
icon: material/numeric-3
---

# Embeddings


**From Data to Numbers: The Universal Concept of Embeddings 🔡🖼️🔊**

**Objective:** To understand the critical process of **embedding**, which converts all types of data into a numerical format that an AI can understand. By the end of this section, you will be able to explain how this concept applies not just to text but to images and other data types, unlocking advanced applications like multimodal AI.


### The Universal Language of the Model: Numbers

In the last section, we learned that the **Transformer** architecture allows a model to understand the relationships between words in a sentence. This leads to a fundamental question: How does a computer, which only understands numbers, begin to comprehend something as abstract as a word or an image?

The answer is a process that acts as a universal translator, converting any type of data into the only language the model speaks: the language of numbers. This process is called **embedding**.

### Starting with Text: How Words Become Vectors

Let's begin with the most familiar data type: **text**. To prepare language for a Transformer, the model takes a few key steps\.

1.  **Tokenization:** The system first breaks a sentence down into smaller pieces, like words or subwords, called **tokens**. For example, the sentence `"The cat sat"` becomes three tokens: `"The", "cat", "sat"`.

2.  **Embedding:** Next, each token is converted into a list of numbers called a **vector**. This vector is not random; it's a high-dimensional mathematical representation of the token's meaning. Think of it as a coordinate on a giant, multi-dimensional map of meaning. On this map, tokens with similar meanings (like `"happy"` and `"joyful"`) are located close to each other, while dissimilar tokens (`"happy"` and `"car"`) are far apart.

3.  **Positional Encoding:** Because the attention mechanism looks at all the tokens at once, the model needs a way to understand the original word order. Positional encoding adds information to each vector that signals its position in the original sequence.

!!! info "The Token as a Business Metric 🪙"

    Beyond being a technical step, the **token** is the fundamental unit of measurement in the world of LLMs. As a business leader or product manager, you will encounter it constantly in three critical areas:

    1.  **Context Window:** A model's memory, or **context window**, is measured in tokens (e.g., 128,000 tokens). This number dictates how much information—including instructions, user history, and reference documents—the model can consider at one time. A larger context window is more powerful but can be more expensive to operate.

    2.  **Billing and Cost:** When you use an LLM via an API, you are billed per token. Pricing is often broken down into:
        * **Input Tokens:** The tokens you send to the model (your prompt).
        * **Output Tokens:** The tokens the model generates for you (the response).
        Understanding this allows you to forecast costs and design more efficient applications.

    3.  **Performance:** The number of tokens in a prompt directly impacts how long it takes for the model to generate a response (latency). Longer inputs require more computation.

    !!! tip "A rule of thumb: For English text, one token is roughly ¾ of a word. So, 100 tokens is about 75 words."

### The Leap to Multimodality: The Universal Translator

Here is the concept that unlocks the power of modern AI: the process of creating an **embedding** is a universal one. The same fundamental idea of turning data into a meaningful numerical vector applies to everything, not just text.

This is the foundation of **multimodal AI**—the ability of a single model to understand and process information from multiple data types at once. The **Gemini** family of models, for example, can take interleaved sequences of text, images, audio, and video as input.

Various inputs like text, audio, and images are all converted into a common numerical format before being fed into the Transformer.

Think of the embedding process as a **universal translator**. Its job is to take any form of data—a word, the pixels in a photo, a soundwave from an audio file—and convert it into a vector within a shared "meaning space." In this space, the vector for the *word* "apple" will be mathematically close to the vector generated from a *picture* of an apple.

### Why This Matters for Business: Unlocking New Applications

This ability to represent different data types in a shared numerical language is what enables a new frontier of powerful applications.

#### A Killer App for Embeddings: Semantic Search

To understand the immediate business value of embeddings, let's contrast a familiar tool with its new, AI-powered counterpart.

You're familiar with traditional **keyword search** (like using Ctrl+F in a document). It's great at finding exact matches. If you search for the word "slow," it will find every instance of "slow." However, it will completely miss related concepts like "laggy," "unresponsive," or "takes forever to load."

**Semantic search**, powered by embeddings, is different. It is **search by meaning, not by keyword.**

Here’s how it works:

1.  **Index the Data:** First, you convert your entire library of documents—internal wikis, customer support tickets, market research reports—into numerical embeddings and store them in a specialized "vector database." This creates the "meaning map" of your data.
2.  **Query the Data:** When a user types a query (e.g., "complaints about poor performance"), the system converts that query into an embedding.
3.  **Find Similar Meanings:** The system then finds the document embeddings that are mathematically closest to the query embedding on the map.

This unlocks powerful new capabilities for core business tasks:

* **Insight Generation:** A product manager can search a database of thousands of customer reviews for the *concept* of "difficult to use." Semantic search will instantly surface feedback that includes phrases like "the user interface is confusing," "I couldn't find the settings menu," and "the onboarding process was a nightmare"—deep insights that keyword search would have missed.

* **Information Extraction:** An R&D team can search a library of scientific papers with a high-level question about a new chemical process. The system will find relevant papers that describe the process using different terminology, dramatically accelerating research.

* **Creative Ideation for Marketing:** A marketing team can take a new slogan and semantically search a database of past campaigns to find examples with a similar *emotional tone* or *brand voice*, even if the wording is completely different.

#### Connecting to Advanced Applications

This same core concept of matching meaning via embeddings is the engine for even more advanced applications:

* **Connecting to Robotics:** This is how a generative AI model can power a robot. The AI processes a verbal command (**text embedding**), sees an object on the table (**image embedding**), and reasons across both data types to generate a plan of action. The model can connect the spoken word "apple" to the object in front of it because their respective vector embeddings are similar.


<figure markdown="span">
  [![Gemini Robotics: Bringing AI to the physical world](http://img.youtube.com/vi/4MvGnmmP3c0/0.jpg){ width="300" }](https://www.youtube.com/watch?v=4MvGnmmP3c0)
  <figcaption>Video: Gemini Robotics - Bringing AI to the physical world</figcaption>
</figure>


* **Connecting to RAG:** This concept is also the foundation for **Retrieval Augmented Generation (RAG)**, a technique we'll cover later. A user's question is turned into an embedding and used to search a database for documents with the most similar embeddings (i.e., the most similar meaning), which are then fed to the model to generate a well-informed answer.


!!! success "Key Takeaway" 

    Understanding embeddings as a universal translator is crucial for identifying innovative business opportunities. The strategic question is no longer "What can I do with my text data?" but rather "How can I combine all my data streams—text from customer reviews, images of products, audio from support calls—to create a single, smarter, and more context-aware AI application?"
