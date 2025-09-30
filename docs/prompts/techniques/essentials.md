---
icon: material/numeric-2
---


# The Essential Foundations

In the previous section, we established a mindset for tackling complex problems. Now, we'll get practical. Building a single, effective prompt is a good start, but building a real-world AI product requires making those prompts scalable, maintainable, and ready to be integrated into an application.

This lesson covers two key pillars of operationalizing prompts. First, we'll learn **how to create reusable blueprints for our prompts using templates**. Second, we'll explore the **technical environments where these templates are deployed**, focusing on the crucial differences between Text Completion and Chat API models.


## Prompt Templates & Scalability

**Moving Beyond the Playground 🚀**

Tools like Google AI Studio are fantastic "playgrounds" for rapid prototyping. However, when you move from experimenting to building a real software product, your approach needs to mature.

In a real application, you can't just have prompts scattered around in your code. This is inefficient, hard to maintain, and impossible to scale. The professional approach is to use **prompt templates**, which are reusable, pre-defined text structures with placeholders for dynamic information. Using variables in prompts allows you to make them more dynamic.

### **A Practical Example: From Static Prompt to Template**

Let's see this in action. Imagine you're building a feature for a travel app that gives users a fun fact about a city they search for.

**The Static (Hardcoded) Prompt**

Your first attempt in the playground might look like this:

```
You are a travel guide. Tell me a fact about the city: Amsterdam
```

This works for a single case, but it's not reusable.

**The Template-Based Prompt**

A much better approach is to create a template with a **variable**.

```
You are a travel guide. Tell me a fact about the city: {city}
```

Now, you have a single, reusable blueprint. Your application's code can dynamically insert any city name into the `{city}` variable before sending the completed prompt to the LLM. Here’s how simple it is to use this template in Python:

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

!!! success "Templates"

    As a Product Manager, insisting on the use of prompt templates is critical for building a scalable AI product. It's a strategic practice with several key benefits:

    * **Separation of Concerns:** Templates allow your team to separate the **prompt logic** (the instructions) from the **data** (the user-specific information). This means your prompt engineers can refine the prompt's wording without changing the application's core code.
    * **Easier A/B Testing:** Want to see if a more "witty" persona improves engagement? With templates, you can easily test different versions of a prompt against each other to find the most effective one.
    * **Maintainability:** If you need to update a prompt that's used in 10 different places, templates let you do it in one central location, saving time and reducing errors.


## Completions & Conversations 💬

How you *use* a template depends on the type of interaction model you're working with. The two most common are **Text Completion** and **Chat**.

### **Simple Text Completion vs. Multi-Round Chat**

  * **Text Completion Model:** Think of this as the world's most powerful auto-complete. You provide a single block of text (your prompt), and the model's only job is to predict the text that should follow. It is **stateless** and has no memory of past interactions.
  * **Chat Model:** This model is designed for back-and-forth dialogue. It is **stateful**, meaning it is designed to remember the history of the conversation and use that context to inform its next response. This powers applications like chatbots and virtual assistants.

### **The Role of System Instructions**

A key feature, particularly of chat models, is the **System Instruction**. This is a high-level instruction that sets the context, persona, and rules for interactions. It acts as a mission briefing for your AI.

System instructions can operate at two levels, providing a powerful way to govern model behavior:

  * **Application-Level:** You can set a global, default instruction that defines the core personality and safety constraints for your entire service. This "base instruction" is automatically applied to every new conversation, ensuring a consistent brand voice.
  * **Session-Level:** For a specific conversation, you can add a more specific instruction that augments or temporarily overrides the global one to handle a particular task.

**Example Application-Level System Instruction:**

!!! example "System Instruction for a Support Bot"
  
    "You are 'Tango', a helpful support bot for a software company. Your tone must always be patient, friendly, and professional. Never apologize for the product's behavior. Instead, provide clear, step-by-step instructions to help the user."

### Example: The "Partial Input" Strategy in Different APIs

Let's use the simple **partial input completion** strategy to see how differently it's implemented in a text completion vs. a chat API.

**Partial Input in a Text Completion API**

You create a single string that ends mid-thought. The model simply finishes it.

```python
# The entire prompt is one string
prompt_string = """
The three most important qualities of a great Product Manager are:
1. Deep Customer Empathy
2. Clear Communication Skills
3. """

# The model's output would be something like: "Strategic Thinking"
```

**Partial Input in a Chat API**

You can't just send an unfinished sentence. You must conversationally guide the model by manually constructing a chat history.

```python
# The prompt is a list of conversation turns
chat_prompt = [
    {
        "role": "user",
        "parts": ["What are the three most important qualities of a great Product Manager? Give me just the first two for now."]
    },
    {
        "role": "assistant",
        "parts": ["Of course. The first two are:\n1. Deep Customer Empathy\n2. Clear Communication Skills"]
    },
    {
        "role": "user",
        "parts": ["Perfect, now what's the third one?"]
    }
]

# The model, having the full context, will generate the next assistant message, 
# which would be something like: "The third most important quality is Strategic Thinking."
```