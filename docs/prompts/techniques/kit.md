---
icon: material/numeric-3
---


**Core Prompting Techniques**

Now that you understand how to create scalable templates and the environments they operate in, it's time to learn the core "recipes" of prompt engineering. These techniques are your fundamental tools for translating a business need into a clear, effective instruction for an LLM.

We will cover three foundational techniques that progress from simple to more complex, forming the basis of most of the advanced prompting work you will ever do.


## 1\. Zero-Shot Prompting 

**The Direct Instruction 🎯**

Zero-shot prompting is the simplest and most direct technique. It involves providing a task description to the model without giving it any prior examples of the desired output. This technique relies entirely on the model's vast pre-existing knowledge and its ability to follow instructions.

**Example: Simple Classification**

Imagine you need to classify customer reviews. A zero-shot prompt would look like this:

```
Classify movie reviews as POSITIVE, NEUTRAL or NEGATIVE. 

Review: "Her" is a disturbing study revealing the direction humanity is headed if AI is allowed to keep evolving, unchecked. I wish there were more movies like this masterpiece. 

Sentiment:
```

The model, using its built-in understanding of language and sentiment, will analyze the text and (in this case) likely output "POSITIVE". 

!!! tip "When to Use Zero-Shot"

    Zero-shot prompting is your go-to technique for straightforward, common tasks where the model already has strong capabilities. It works best for:

      * Simple text classification (e.g., sentiment analysis).
      * Basic text summarization.
      * Language translation.
      * Answering general knowledge questions.


## 2\. Few-Shot Prompting
**Learning by Example 🧩**

When a task requires a specific output structure or has nuances that are hard to describe with words alone, zero-shot prompting may not be reliable enough. This is where **few-shot prompting** shines.

This technique involves providing the model with multiple examples (or "shots") that demonstrate the task and the expected output format. By showing the model a pattern, you guide it to produce a response that precisely matches your requirements.

**Example: Parsing Unstructured Data into JSON**

Imagine you are building a feature to process pizza orders from a chatbot. You need the final output to be in a structured JSON format that your application can easily read.

A few-shot prompt would look like this:

```
Parse a customer's pizza order into valid JSON: 

EXAMPLE:
I want a small pizza with cheese, tomato sauce, and pepperoni. 
JSON Response:
{
 "size": "small",
 "type": "normal",
 "ingredients": [["cheese", "tomato sauce", "peperoni"]]
} 

EXAMPLE:
Can I get a large pizza with tomato sauce, basil and mozzarella 
JSON Response:
{
 "size": "large",
 "type": "normal",
 "ingredients": [["tomato sauce", "bazel", "mozzarella"]]
} 

Now, I would like a large pizza, with the first half cheese and mozzarella. And the other tomato sauce, ham and pineapple. 
JSON Response:
```

Given these examples, the model understands the desired schema and will correctly parse the final order into the structured JSON format you've demonstrated.

!!! tip  "Best Practices for Few-Shot Examples"

    **Quality is Crucial:** Your examples must be accurate and well-written. A single mistake can confuse the model and lead to undesired output.

    **Start with 3-5 Examples:** As a general rule, three to five examples are a good starting point for most tasks.

    **Mix It Up:** For classification tasks, make sure you mix up the possible response classes in your examples. This prevents the model from simply learning the order of the examples rather than the underlying features of each class.


## 3\. Chain-of-Thought (CoT) Prompting

**Showing Your Work 🧠**

For tasks that require logic, math, or multi-step reasoning, even few-shot prompting can sometimes fail. LLMs can often struggle with these problems because they try to jump directly to the answer. **Chain-of-Thought (CoT) prompting** is a powerful technique that solves this by prompting the model to generate intermediate reasoning steps before giving a final answer.

You can often trigger this behavior simply by adding the phrase "Let's think step by step" to your prompt.

**Example: Solving a Reasoning Problem**

Consider this simple math riddle:

**Prompt without CoT:**

```
When I was 3 years old, my partner was 3 times my age. Now, I am 20 years old. How old is my partner? 
```

**Typical (Incorrect) Output:** `63 years old` 

The model tries to perform a simple multiplication and gets it wrong. Now, let's use CoT.

**Prompt with CoT:**

```
When I was 3 years old, my partner was 3 times my age. Now, I am 20 years old. How old is my partner? Let's think step by step. 
```

**Correct Output with Reasoning:**

```
1. When I was 3 years old, my age was 3 years. 
2. My partner's age at that time was 3 times my age, which means my partner's age was 3 * 3 = 9 years. 
3. Now, I am 20 years old, which means my age has increased by 20 - 3 = 17 years since I was 3 years old. 
4. Since my partner's age was 9 years when I was 3 years old, and my age has increased by 17 years, my partner's age must have also increased by 17 years. 
5. Therefore, my partner's current age is 9 + 17 = 26 years. 

So, my partner is 26 years old. 
```

By forcing the model to decompose the problem, it arrives at the correct answer.

!!! success "Interpretability"

    CoT provides a massive benefit for product development: you can see the model's **"thought process"**. If the model gets an answer wrong, you can examine its reasoning steps to understand *where* the logic failed, making it much easier to debug and improve your prompt.

###  Self-Consistency

Self-consistency is a powerful technique that builds on CoT to further improve accuracy on complex reasoning tasks. It works by running the same CoT prompt multiple times with a higher `temperature` to generate several different reasoning paths. It then takes a majority vote to select the most consistent answer among all the paths. This reduces the chance of a single flawed reasoning chain leading to an incorrect result.


**Advanced Techniques & Future Directions**


You now have a solid grasp of the foundational prompting techniques. In this section, we'll look ahead to the cutting edge. These advanced techniques are designed to solve complex problems that require a higher level of abstraction, reasoning, and even interaction with external sources of information.

Mastering these concepts will prepare you to design the next generation of sophisticated AI-powered products.


## 4\. Step-Back Prompting 
**Seeing the Forest for the Trees 🌲**

Sometimes, a direct prompt, even a well-crafted one, can lead to a narrow or generic answer. **Step-back prompting** is a technique that improves performance by first prompting the LLM to consider a general question or abstract concept related to the specific task at hand.  This "step back" allows the model to activate relevant background knowledge and reasoning processes before attempting to solve the specific problem. 

By considering the broader principles first, the model can generate more accurate and insightful responses. 

### **Example: Generating a Creative Storyline**

Imagine you need to generate a creative storyline for a new video game level.

**A Traditional Prompt:**

```
Write a one paragraph storyline for a new level of a first-person shooter video game that is challenging and engaging.
```

**A Typical, Generic Output:**

!!! quote "" 

    The level begins with the player's squad being ambushed in a dense urban area by a relentless enemy faction. Players must fight their way through a maze of back alleys and dilapidated buildings, utilizing stealth and precision to eliminate enemy forces... 

This is functional but uninspired. Now, let's try the step-back approach.

**Step 1: The "Step-Back" Prompt to Generate Concepts**

First, we ask the model a more general question to generate some creative themes:

```
Based on popular first-person shooter action games, what are 5 fictional key settings that contribute to a challenging and engaging level storyline...?
```

**Step 2: The Final Prompt, Using the Concepts as Context**

Now, we use the output from our first prompt as rich context for our original request:

```
Context: 5 engaging themes for a first person shooter video game:
1. Abandoned Military Base...
2. Cyberpunk City...
3. Alien Spaceship...
4. Zombie-Infested Town...
5. Underwater Research Facility...

Take one of the themes and write a one paragraph storyline for a new level of a first-person shooter video game...
```

**A Richer, More Specific Output:**

!!! quote ""

    In the heart of a murky abyss, lies a dilapidated underwater research facility, standing as a testament to human ambition and its disastrous consequences. Shrouded in darkness...the facility is now a breeding ground for a nightmare borne from the deep sea. The player, an elite marine equipped with advanced diving gear...must navigate treacherous corridors, solve cryptic puzzles, and confront gruesome sea monstrosities that lurk in the depths... 

By first generating high-level concepts and then using them as context, we guided the model to produce a far more creative and compelling result.


## 5\. ReAct: Reason and Act
**Synergizing Reason and Action ⚡**

**ReAct** is a paradigm that dramatically expands what an LLM can do. It enables models to solve complex tasks by combining natural language **reasoning** with the ability to take **actions** using external tools (like a search engine, calculator, or code interpreter). 

ReAct works in a simple but powerful loop:

1.  **Thought:** The model reasons about the problem and determines what action it needs to take.
2.  **Action:** The model uses an external tool to get information.
3.  **Observation:** The model receives the output from the tool and uses this new information to update its reasoning and determine the next thought. 

#### **Example: Answering a Multi-Part Factual Question**

Imagine you ask a model, "How many kids do the band members of Metallica have?" An LLM's internal knowledge might be outdated or incomplete. With ReAct, it can use a search engine to find the answer. The process looks like this:

!!! quote ""

    **\> Entering new AgentExecutor chain...**<br/>
    **Thought:** I need to find out who the members of Metallica are first.<br/>
    **Action:** Search<br/>
    **Action Input:** current members of Metallica<br/>
    **Observation:** James Hetfield, Lars Ulrich, Kirk Hammett, Robert Trujillo<br/>
    **Thought:** Now I need to find out how many kids each member has. I'll start with James Hetfield.<br/>
    **Action:** Search<br/>
    **Action Input:** How many kids does James Hetfield have?<br/>
    **Observation:** three children<br/>
    **Thought:** 1/4 Metallica band members have 3 children. Now for Lars Ulrich.<br/>
    **Action:** Search<br/>
    **Action Input:** How many kids does Lars Ulrich have?<br/>
    **Observation:** 3<br/>
    **Thought:** 2/4 Metallica band members have 6 children...<br/>
    ...*this process continues for all members*...<br/>
    **Thought:** 4/4 Metallica band members have 10 children<br/>
    **Final Answer:** 10 <br/>

This ability to interact with external tools makes the model dramatically more powerful and factually grounded.

**🤖 The Birth of AI Agents**

The ReAct paradigm is a fundamental step toward creating **AI agents**. An agent is more than just a text generator; it's an autonomous system that can reason about a goal and take a sequence of actions in a digital or physical environment to achieve it.

As a product manager, understanding ReAct is crucial because it represents a shift from building features that *answer questions* to building systems that *accomplish tasks*. Whether it's an AI travel agent that can book flights or a financial analyst that can execute trades, the underlying logic often starts with this "Reason and Act" loop.