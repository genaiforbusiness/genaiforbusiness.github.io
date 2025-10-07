---
icon: material/numeric-5
---


# 👩‍💻 Hands-On Lab & Workflow

Theory is essential, but practice is where learning is forged. In this section, we will move from concepts to code-free execution. You will take on the role of a product manager tasked with creating a "smart" e-commerce feature. We will use Google AI Studio for this lab, as it provides a user-friendly interface for experimenting with the advanced capabilities we've discussed.

#### **Lab Goal: Chaining Capabilities for a Real-World Task**

The objective of this lab is to experience a complete, multi-step AI workflow. We will chain together several distinct model capabilities to solve a common business problem. Specifically, you will learn how to:

1.  Use **Image Understanding** to analyze a product photo.
2.  Leverage **Structured Output (JSON)** to create reliable, machine-readable data.
3.  Use that structured data as **Context** for a creative **Text Generation** task.

This process mirrors how a real AI-powered application works: one model's output becomes the input for the next step in the process.

#### **The Scenario: The Smart Product Description Generator**

Imagine you are a product manager at an e-commerce company. Your company has thousands of product images, but the marketing descriptions are often inconsistent or missing entirely. Writing them manually is slow and expensive.

Your task is to prototype a feature that can **automatically generate a compelling marketing description directly from a product image.**

This workflow has two main parts:

  * **Part 1: The Analyst AI:** An AI process that "looks" at a product image and extracts its key features into a structured format.
  * **Part 2: The Copywriter AI:** An AI process that takes the structured features and writes creative, persuasive marketing copy.

#### **Step-by-Step Guide in Google AI Studio**

**Preparation:**

  * Open [Google AI Studio](https://aistudio.google.com/) in your web browser and sign in.
  * Find a product image online that you want to work with. A clear photo of a single item works best (e.g., a watch, a backpack, a pair of shoes, a coffee mug). Save this image to your computer.


**Part 1: The Analyst AI (Image to Structured Data)**

In this step, we will prompt the model to act as a visual analyst.

1.  **Create a New Prompt:** In Google AI Studio, click on **"Create new prompt"**.

2.  **Upload Your Image:** In the prompt window, you will see an "Insert" menu. Click on **Image** and upload the product photo you saved. The image will appear as part of your prompt context.

3.  **Craft the Prompt:** Now, write the prompt that will instruct the model. We need it to do two things: analyze the image and structure the output as JSON. Copy and paste the following prompt into the text box:

    > You are an expert e-commerce analyst. Your task is to analyze the attached product image and extract its key visual features.

    > Your output **must** be a valid JSON object. Do not add any text or explanation before or after the JSON.

    > The JSON object should contain the following keys:

    >   * "productType": (e.g., "wristwatch", "sneaker", "backpack")
    >   * "mainColor": (The dominant color of the product)
    >   * "secondaryColor": (The secondary or accent color)
    >   * "material": (The likely material, e.g., "leather", "canvas", "metal")
    >   * "features": (A brief list of 2-3 key visual features)

4.  **Run and Review:** Click the **"Run"** button. The model should process your image and prompt, and in the output panel, you should see a clean JSON object.

    *Example Output:*

    ```json
    {
      "productType": "wristwatch",
      "mainColor": "brown",
      "secondaryColor": "silver",
      "material": "leather",
      "features": [
        "round silver casing",
        "white watch face",
        "brown leather strap with stitching"
      ]
    }
    ```

    If the output isn't perfect, try running it again or slightly adjusting the prompt. Once you have a clean JSON output, **copy it** to your clipboard.


**Part 2: The Copywriter AI (Structured Data to Creative Text)**

Now we will use our structured data as the input for a creative task.

1.  **Clear the Prompt:** Click the **"X"** to clear the previous prompt and the image. We are starting with a clean slate.

2.  **Craft the New Prompt:** This prompt will define the role of a copywriter and use the JSON you just copied as the core context. Paste the following into the prompt box:

    > You are an expert e-commerce copywriter. Your task is to write a compelling, 30-word marketing description for a product. Use the product features defined in the JSON object below.

    > The tone of the description should be exciting, luxurious, and aimed at a fashion-conscious audience.

    > **Product Data:**

    > ```json
    > [Paste your JSON object here]
    > ```

3.  **Run and Analyze:** Click **"Run"**. The model will now use the structured data you provided to generate a creative marketing description.

    *Example Output:*

    > "Experience timeless elegance. This stunning timepiece features a polished silver case and a rich, genuine leather strap. The perfect blend of classic design and modern sophistication for any occasion."

4.  **Iterate:** Try changing the tone in the prompt. Modify the instruction to be "playful and casual" or "professional and minimalist" and run it again. Observe how the output changes while still being based on the same structured data.


#### **Debrief: Connecting the Lab to Product Management**

Congratulations, you've just prototyped a sophisticated AI-powered workflow\! Let's reflect on what this simple exercise demonstrates about building real-world AI products:

  * **Chaining is Key:** The real power of AI emerges when you chain capabilities. We didn't just do one thing; we created a pipeline where the output of an **analysis** task became the input for a **generation** task.
  * **Structured Data is the Glue:** The JSON object was the critical "glue" between our two AI agents. It was the predictable, machine-readable contract that allowed the "Analyst" to hand off its work to the "Copywriter" reliably. Without this step, the workflow would be fragile and unpredictable.
  * **You are the System Designer:** As a product manager, your job is to design these workflows. You decide what the steps are, what information needs to be passed between them, and what the final output should achieve. Prompt engineering isn't just about writing a single instruction; it's about architecting these multi-step systems.