---
icon: material/numeric-4
---


#  Multimodal Capabilities

Welcome to one of the most visually impressive and creatively disruptive areas of modern AI: **multimodality**. A multimodal model is one that can understand and generate content in more than one format, or "modality." It can process not just text, but also images, audio, and video.

This capability is what allows an AI to "see" the world through a photo, "listen" to a query, and "create" a novel image from a simple description. To understand how a model trained on language can achieve this, we first need to grasp a core concept: **embeddings**.


**Understanding Embeddings**

You can't feed pixels or soundwaves directly into a language model. The model's "brain" is built for mathematics, not for sight or sound. So, to work with different types of media, the model first needs to translate everything into a common, mathematical language. This universal language is made of **embeddings**.

**What is an Embedding? A Universal Language for Data**

An **embedding** is a numerical representation of a piece of content. It's a list of numbers (a vector) that captures the semantic essence or meaning of that content. Think of it like a highly detailed set of coordinates on a massive "map of meaning."

* The word "dog" has an embedding.
* A picture of a golden retriever also has an embedding.
* The sound of a dog barking has an embedding.

Crucially, on this map, concepts that are semantically similar are located close to each other. The embedding for the word "dog" will be mathematically close to the embedding for the word "puppy" and also close to the embedding for the *picture* of a golden retriever. This is the key that unlocks multimodality.

**How Encoding and Decoding Works**

The model uses two key components to work with embeddings:

1.  **The Encoder:** This is the part of the model that acts as a universal translator. It takes an input—text, image, audio—and "encodes" it into its numerical embedding. It reads the content and finds its precise coordinates on the map of meaning.
2.  **The Decoder:** This component does the reverse. It takes an embedding (a set of coordinates) and "decodes" it back into content. A **text decoder** will look at the coordinates and generate the most likely words associated with that meaning. An **image decoder** will look at the same coordinates and generate the pixels most likely to form a picture of that meaning.



This two-step process is how a text prompt can become a picture. Your prompt is first encoded into an embedding, and then an image decoder uses that same embedding as its instruction set for generating pixels.


## **Image & Video Understanding**

This is the model's ability to "see"—to take visual media as an input and analyze its content. It's the practical application of the encoder. The model converts your uploaded image or video into an embedding and then uses its understanding of that embedding to answer questions about it.

### **👩‍💼 The PM Perspective: Unlocking Insights from Unstructured Visual Data**

For decades, businesses have collected vast amounts of visual data (photos, videos, scans) that have been difficult to analyze at scale. This capability changes that entirely.

1.  **Automating Manual Processes:** Think of the human effort spent on tasks like content moderation (flagging inappropriate images), inventory management (counting products on a shelf), or insurance claims processing (assessing photos of damage). These visual analysis tasks can now be automated, freeing up human capital for higher-value work.
2.  **Unlocking New Data Sources:** Customers are constantly generating visual data on social media. A model can analyze images of people using your product "in the wild," giving you unprecedented insight into how, where, and by whom your products are being used.
3.  **Creating Smart Experiences:** You can build features where the user's camera is the primary input. A retail app could allow a user to take a picture of a piece of furniture they like, and the AI could identify similar items in your store's catalog.

### **Prompting for Analysis: From Description to Extraction**

When prompting for visual analysis, you are essentially asking the model to describe what it "sees" in the embedding. Your prompts should be direct and specific.

* **For general description:** "Describe this image in detail." "What is the main subject of this video?"
* **For counting and identification:** "How many cars are in this photo? Identify the color of each one."
* **For text extraction (OCR):** "Extract the text from the receipt in this image and return it as JSON."
* **For abstract analysis:** "What is the likely mood or sentiment of this image? Is it happy, sad, professional, chaotic?"




## **Image & Video Generation**

This is the most creatively exciting multimodal capability: creating brand-new, original visual media. This is the work of the **decoder**, which translates the embedding of your prompt and any source images into a corresponding set of pixels.

### **👩‍💼 The PM Perspective: A Paradigm Shift for Content & Creativity**

The ability to generate high-quality visual content is changing the economics of marketing, advertising, and design.

1.  **Hyper-Personalization at Scale:** Imagine generating a unique ad creative for every customer segment, or even for every individual user.
2.  **Radical Speed in Prototyping:** Visualize new product concepts, store layouts, or character designs in seconds, dramatically accelerating the creative and product development lifecycle.
3.  **Democratizing Creativity:** Small businesses and individual creators now have access to visual content creation tools that were previously only available to large firms with massive budgets.

To leverage this power, a product manager must understand that not all visual generation tasks are the same. Your prompt design must adapt to the specific use case you are trying to solve. Let's explore the three primary scenarios.


### **Prompting Strategies for Visual Generation**

**Use Case 1: Text-to-Image (Creating from Scratch)**

This is the most common use case: generating a novel image purely from a text description. Here, your prompt is the *entirety* of the creative brief.

* **Prompt Strategy: The Detailed Creative Brief**
    Your goal is to describe the desired **final state** of the image in exhaustive detail. A reliable method is to follow a structured template that covers the core elements of a visual scene: 

!!! example "Example Text-to-Image Prompt Template"

    **A [`medium`] of a [`subject`], [`style`], [`color`/`lighting`], [`composition`]**.

    **Medium:** Start here to anchor the style. Is it a "photograph," a "watercolor painting," a "3D render," or "a charcoal sketch"?
    
    **Subject:** Be highly descriptive. Not just "a car," but "a vintage 1960s convertible sports car."
    
    **Style & Details:** Add artistic and textural modifiers. "Hyperrealistic," "in the style of Van Gogh," "steampunk-inspired," "made of brass and copper gears."
    
    **Color & Lighting:** Describe the mood. "Vibrant, saturated colors," "dark, moody background," "cinematic lighting."
    
    **Composition:** Explain the framing. "Close-up portrait," "wide-angle landscape shot," "from a low angle."

**Use Case 2: Text + Image(s) (Editing, Combining, and Transforming)**

Here, you provide one or more source images along with your text prompt. The model now has both textual and visual context. Your prompt's job is not to describe a whole scene, but to describe the **relationship, modification, or transformation** you want to perform.

**Prompt Strategy: The Direct Command for Transformation**

Your language should be direct, clear, and focused on the change you want to see.

!!! tip "For Animating a Single Image (Image-to-Video)"

    The prompt must describe **motion**. Use strong, action-oriented verbs. The best prompts are concise and focused on the desired action.
        
    * **Example:** For a photo of a mountain lake, a prompt like **"Make the water shimmer and the clouds drift slowly to the right"** is ideal. The prompt describes the *change* to the existing context (the image).

!!! tip "For Combining Multiple Images (Style Transfer, Blending)"

    The prompt must describe the **manner of combination**. You specify the role of each image.
        
    * **Example:** With an image of a person (Image A) and an image of a Van Gogh painting (Image B), the prompt would be **"Apply the style of Image B to Image A."**

!!! tip "For Editing an Image (Inpainting/Outpainting)"

    You provide an image and a mask (a selected area), and the prompt describes what to do within that area.
        
    * **Example:** With an image of a person holding an apple, you could mask the apple and provide the prompt **"Change the apple to an orange."**

**Use Case 3: Image-Only (Visual Similarity)**

In some cases, you may not even need a text description of image in a prompt. You can provide an image as the sole input to a model and ask it to find or generate visually similar images. This is a common feature in e-commerce ("Find more shirts like this one"). While not a "prompting" technique in the textual sense, it's a core multimodal capability that relies on the model's understanding of embeddings to find images that are "close" to the source image on the map of meaning.

By understanding these different use cases, you can tailor your prompt strategy to the specific task at hand, moving fluidly between the roles of a detailed creative director, a direct editor, and a visual curator.


See Google's blog posts linked below for more examples:

- [10 examples of our new native image editing in the Gemini app](https://blog.google/products/gemini/gemini-nano-banana-examples/ )

- [3 ways to use photo-to-video in Gemini](https://blog.google/products/gemini/gemini-photo-to-video-tips/ )


## **The PM's Choice: Integrated vs. Specialist Models**

As we've seen, models like Gemini can generate images directly as part of their multimodal capabilities. However, you will also encounter powerful, standalone models designed *exclusively* for image generation, such as Google's Imagen, OpenAI's DALL-E 3, or Midjourney.

This creates a critical strategic choice: when should your product use the convenient, built-in capabilities of a multimodal model versus calling a separate, specialized service?

Think of it like the camera on your smartphone versus a professional DSLR camera.

* **Integrated Models (The Smartphone Camera):** The image generation capability built into Gemini is incredibly convenient, fast, and surprisingly powerful. It's always with you, seamlessly integrated into the tool you're already using, and perfect for a huge range of tasks where "good enough" is great.
* **Specialist Models (The Professional DSLR):** A dedicated model like Imagen is a specialist tool. It does one thing—image generation—and aims to do it at the absolute state-of-the-art level. It offers the highest possible quality, the most granular control over style and composition, and the most advanced features.

**Is This Distinction Common?**

Yes, this is a dominant pattern across the industry.

* **OpenAI** has its GPT family of models (e.g., GPT-4o) which have native, integrated image generation. This capability is powered by their dedicated, state-of-the-art image model, **DALL-E 3**. While the experience is seamless in a product like ChatGPT, they are distinct models working in concert.
* **Anthropic's Claude** models, as of now, are world-class at *understanding* images but do not have native image *generation* capabilities. To create a visual with Claude, your application *must* use function calling to connect to an external, specialist service like Stability AI or Midjourney.

**The Product Manager's Decision Framework**

Your job is to decide which tool is right for the job. Here’s a framework to guide your thinking:

| **Use the Integrated Model (e.g., Gemini) when...** | **Use a Specialist Model (e.g., Imagen) when...** |
| --------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| **Speed and Simplicity are paramount.** (e.g., rapid prototyping, simple blog illustrations) | **Image Quality is the top priority.** (e.g., hero images for a marketing campaign, product design) |
| **The task is part of a larger, seamless workflow.** (e.g., "Summarize this text, then make an image for it.") | **You need fine-grained, professional control.** (e.g., specific art direction, style consistency) |
| **"Good enough" quality is sufficient for the user experience.** (e.g., generating icons or simple diagrams) | **You need the absolute latest, state-of-the-art features.** (e.g., realistic text in images)    |
| **You want to minimize architectural complexity and API calls.** | **You want the flexibility to swap out the best-in-class provider for that specific task.** |

Ultimately, there is no single right answer. The choice depends entirely on your product's specific needs, your users' expectations for quality, and your technical and budget constraints. A skilled product manager knows both types of tools are in their toolkit and understands when to reach for the convenient smartphone and when to set up the professional DSLR.