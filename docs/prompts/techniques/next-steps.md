---
icon: material/numeric-5
---


# Conclusion & Next Steps

Congratulations on completing this lesson. You have moved from the basic anatomy of a prompt to a full, professional workflow. You have a **mindset** for decomposing and composing problems, you know how to build scalable **templates**, you have a core **toolkit** of prompting techniques, and you have a **workflow** for developing and documenting your work.

With these techniques, you can guide LLMs to perform incredibly powerful and complex tasks.

## **Next Steps**

Now that you have a powerful toolkit of techniques, the next logical step is to understand the specific strengths, weaknesses, and characteristics of the models you'll be prompting. In our next module, **"Aligning Prompt Design with Model Capabilities,"** we will explore how to select the right model for your prompt and how to tailor your prompt for the model you've chosen, ensuring you get the best possible performance for your product.


### **💡 Project Takeaways**

As you begin working on your group course project, keep these key takeaways from this module in mind:

  * **Start Simple, Then Iterate:** Don't jump to the most complex technique first. Start with a simple zero-shot prompt. If it's not reliable enough, then upgrade to a few-shot prompt or introduce Chain-of-Thought. The goal is to find the simplest technique that reliably solves the problem.
  * **Few-Shot is Your Superpower for Structure:** If your project requires the LLM to output structured data (like JSON) that your application can use, a well-crafted few-shot prompt is almost always the best approach.
  * **Document From Day One:** Use the documentation template from this lesson to log your team's prompt experiments. This will save you countless hours when you need to debug, hand off work, or test your system against a new model.
  * **Use CoT for Any "Thinking":** If any feature in your project requires the model to reason, perform calculations, or follow a logical sequence, use Chain-of-Thought prompting to improve accuracy and make the model's reasoning process visible for debugging.


### **🚀 Try It Yourself**

The best way to master these techniques is to use them. Here are some activities to help you practice.

#### **In Google AI Studio**

1.  **Objective:** Experience the difference in reliability between zero-shot and few-shot prompting.
2.  **Task:** Create a prompt that extracts a `book_title` and `author` from an unstructured sentence and returns the output in a clean JSON format.
3.  **Part 1 (Zero-Shot):** Write a prompt that only *describes* the task. For example: `Extract the book title and author from the following sentence and format it as JSON: "I just finished reading The Hobbit by J.R.R. Tolkien."` Run it a few times. Does it always return valid JSON?
4.  **Part 2 (Few-Shot):** Now, create a new prompt. This time, provide 2-3 examples of sentences and their corresponding JSON outputs before giving it the final sentence to process. Observe how the consistency and reliability of the output improve dramatically.

#### **In Google Colab**

To see these techniques implemented in Python with the Gemini API, we highly recommend exploring the examples in the official Gemini Cookbook on GitHub. You can open these notebooks directly in Google Colab to run and modify the code yourself.

  * **Link:** [**Gemini Prompting Examples Cookbook**](https://github.com/google-gemini/cookbook/tree/main/examples/prompting)
  * **Suggested Notebooks:**
      * The **`Few-shot prompting`** notebook is a great place to start.
      * The **`Chain-of-thought`** notebook shows you how to implement CoT in code to solve more complex problems.

-----

### **📚 References & Further Reading**

1.  **Prompt Engineering Whitepaper:** A comprehensive guide covering the topics from this module and more. Many examples in this lesson are sourced from this whitepaper. 
      * [`https://www.kaggle.com/whitepaper-prompt-engineering`](https://www.google.com/search?q=%5Bhttps://www.kaggle.com/whitepaper-prompt-engineering%5D\(https://www.kaggle.com/whitepaper-prompt-engineering\))
2.  **Gemini API Documentation - Prompting Strategies:** Google's official documentation with tips and strategies.
      * [`https://ai.google.dev/gemini-api/docs/prompting-strategies`](https://www.google.com/search?q=%5Bhttps://ai.google.dev/gemini-api/docs/prompting-strategies%5D\(https://ai.google.dev/gemini-api/docs/prompting-strategies\))
3.  **Gemini API Reference:** The technical API documentation for generating content, useful when you start coding.
      * [`https://ai.google.dev/api/generate-contentAPI`](https://www.google.com/search?q=%5Bhttps://ai.google.dev/api/generate-contentAPI%5D\(https://ai.google.dev/api/generate-contentAPI\))