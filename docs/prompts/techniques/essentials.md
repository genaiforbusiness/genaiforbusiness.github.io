---
icon: material/numeric-2
---


# The Es

In the previous section, we established a mindset for tackling complex problems. Now, let's build on that by learning the single most important practice for turning a one-off prompt into a professional, application-ready asset: **prompt templates**.

-----

### Moving Beyond the Playground 🚀

Tools like Google AI Studio are fantastic "playgrounds." [cite\_start]They allow you to rapidly test ideas and experiment with prompts without writing any code[cite: 846]. However, when you move from prototyping to building a real software product, your approach needs to mature.

In a real application, you can't just have prompts scattered around in your code. This is inefficient, hard to maintain, and impossible to scale. The professional approach is to use **prompt templates**, which are reusable, pre-defined text structures with placeholders for dynamic information.

Think of a template as a blueprint for your prompt. It contains the core instructions that stay the same, with "blanks" that you fill in with specific data—like a customer's name, a product ID, or a piece of text to be analyzed—before sending it to the model. [cite\_start]Using variables in prompts allows you to make them more dynamic[cite: 815].

-----

### A Practical Example: From Static Prompt to Template

Let's see this in action. Imagine you're building a feature for a travel app that gives users a fun fact about a city they search for.

#### **The Static (Hardcoded) Prompt**

Your first attempt in the playground might look like this:

```
You are a travel guide. Tell me a fact about the city: Amsterdam
```

This works for a single case, but it's not reusable. To get a fact about a different city, you'd have to create a whole new prompt.

#### **The Template-Based Prompt**

[cite\_start]A much better approach is to create a template with a placeholder, often called a **variable**[cite: 818].

```
You are a travel guide. Tell me a fact about the city: {city}
```

Now, you have a single, reusable blueprint. Your application's code can dynamically insert any city name into the `{city}` variable before sending the completed prompt to the LLM.

For students with some Python experience, here’s how simple it is to use this template in code:

```python
def get_city_fact_prompt(city_name):
  """
  This function populates a prompt template with a specific city name.
  """
  prompt_template = "You are a travel guide. Tell me a fact about the city: {city}"
  
  # The .format() method replaces the {city} placeholder with the city_name variable
  final_prompt = prompt_template.format(city=city_name)
  
  # This final_prompt is now ready to be sent to an LLM API
  return final_prompt

# Example usage:
prompt_for_tokyo = get_city_fact_prompt("Tokyo")
print(prompt_for_tokyo)

# Output:
# You are a travel guide. Tell me a fact about the city: Tokyo
```

[cite\_start]This approach is clean, scalable, and makes your prompts a manageable part of your application[cite: 820].

-----

> ### 👩‍💼 The PM Perspective on Templates
>
> As a Product Manager, understanding and insisting on the use of prompt templates is critical for building a scalable AI product. It's not just a technical detail; it's a strategic practice with several key benefits:
>
>   * **Separation of Concerns:** Templates allow your team to separate the **prompt logic** (the instructions for the LLM) from the **data** (the user-specific information). This means your writers and prompt engineers can refine the prompt's wording without having to change the application's core code.
>
>   * **Easier A/B Testing:** Want to see if a more "witty" or "formal" persona improves user engagement? With templates, you can easily test different versions of a prompt against each other to find the most effective one, all while using the same underlying data.
>
>   * **Maintainability:** If you need to update the instructions for a prompt that's used in 10 different parts of your application, templates let you do it in one central place. This saves time and reduces the risk of errors.


I think this may be a good spot to introduce system instructions, the distinction between simple text completion versus multi-round chat, partial input strategy, and how it would translate in text completion API versus chat API (via providing manually constructed chat history).