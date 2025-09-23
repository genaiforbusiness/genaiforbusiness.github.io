---
icon: material/numeric-3
---


# Hands-On Lab in Google AI Studio

In the previous sections, we've discussed the theory behind crafting a great prompt and the control panel that tunes the AI's response. Now, you'll get to apply that knowledge directly.

### 🎯 Lab Objectives

By the end of this lab, you will be able to:

  * Manipulate the **Temperature** setting to control the creativity and tone of an AI's output.
  * Compare a vague prompt to a well-structured prompt to see the difference in output quality.
  * Articulate the **business implications** of these choices from a product manager's perspective.

### Getting Started

1.  In a new browser tab, open [Google AI Studio](https://aistudio.google.com/) and sign in.
2.  Create a new, empty prompt by clicking the **+ New prompt** button.
3.  You should now see the workspace we reviewed in the previous section. You are ready to begin.

-----

### The Scenario ✈️

For today's exercises, you are a **Product Manager for a new AI-powered travel planning app**. Your team is relying on you to develop the prompts that will generate the in-app content for users. Your goal is to create content that is not only accurate but also perfectly aligned with the app's brand and the user's needs.

-----

### Exercise 1: Tuning the Creativity Dial (Temperature)

**Objective:** To observe the direct impact of the **Temperature** setting on the tone and creativity of the model's output.

#### Instructions

1.  In the prompt area of Google AI Studio, paste the following text:
    ```
    Act as a witty travel guide. Write a one-paragraph description of New York City for a first-time visitor.
    ```
2.  **Run A (Factual Mode):**
      * On the right-hand side, find the **Temperature** slider and set it to `0.2`.
      * Leave the other settings (like Top-K and Top-P) at their default values.
      * Click the **Run** button.
      * Copy and paste the generated output into a separate document for later comparison.
3.  **Run B (Creative Mode):**
      * Do not change the prompt.
      * Now, move the **Temperature** slider to `0.9`.
      * Click **Run** again.
      * Copy and paste this new output into your document.

#### Analysis & Discussion

Review the two outputs side-by-side and consider the following questions from your perspective as the product manager:

  * Compare the outputs. What are the key differences in **tone**, **word choice**, and **factual focus** between the low-temperature and high-temperature responses?
  * Which output would you use for the official "About NYC" page inside the travel app? Why is its tone more appropriate for that feature?
  * Which output would be better for a catchy social media post to promote your app? Why does its style serve that purpose better?

-----

### Exercise 2: The Power of a Good Product Spec (Prompt Anatomy)

**Objective:** To demonstrate how a well-structured prompt (a good "spec") produces a more reliable and product-ready result than a vague one.

#### Instructions

1.  **Run A (The Vague Prompt):**
      * Clear the previous prompt.
      * On the right-hand side, ensure your settings are in "factual mode" (e.g., Temp `0.2`, Top-K `40`, Top-P `0.95`).
      * Enter the following vague prompt and click **Run**:
        ```
        things to do in Paris
        ```
      * Observe the output. Note its structure, length, and the type of content it provides.
2.  **Run B (The Well-Structured Prompt):**
      * Keep the same "factual mode" settings.
      * Clear the previous prompt and enter this well-structured prompt:
        ```
        You are a helpful travel assistant. Your audience is a family with two children under 10.

        Generate a list of the TOP 3 family-friendly activities in Paris.

        For each activity, provide a one-sentence description. Return the output as a numbered list.
        ```
      * Click **Run**.

#### Analysis & Discussion

  * Compare the two outputs. Is the result from the "Well-Structured Prompt" immediately usable in your app's user interface?
  * How much manual editing or post-processing would the output from the "Vague Prompt" require to be useful? As a PM, what is the **business cost** of that extra work (e.g., developer time, content editor salaries)?
  * Notice that the second prompt specified the **Persona**, **Context** (audience), **Task**, and **Format**. How did each of these components contribute to the superior quality of the final output?

-----

### Lab Wrap-up

Congratulations on completing the lab. You've now had direct experience with the two most fundamental aspects of prompt engineering: **crafting the prompt's anatomy** and **tuning the model's configuration**. These are the core skills you will use to guide AI models to produce predictable, high-quality, and cost-effective results for your products.

Remember to apply the best practice of **structured logging** by saving your prompt attempts and their results. This will be an invaluable resource as you continue to build more complex AI features.