---
icon: material/tools
--- 

# Tools & Setup

**Understanding Our Digital Workspace**

Before we begin setting up our tools, it’s important to understand the key components of our professional AI development environment. In this course, we are not just using a collection of random tools; we are integrating three core entities—Google's AI platform, the GitHub ecosystem, and secure API keys—to create a digital workspace that mirrors how modern tech teams operate.

## Google
**More Than a Search Engine 🧠**

For many, Google is a search bar. For businesses and developers, it's a global technology powerhouse. Think of it this way: if Google Search is the public library, Google Cloud and AI Studio are the high-tech industrial workshops.

* **Google Cloud Platform (GCP):** This is the enterprise-facing side of Google. It provides companies with powerful, on-demand computing resources, from servers and storage to databases and cutting-edge AI services.
* **Gemini & Google AI Studio:** This is our direct access to Google's state-of-the-art Generative AI models. **Gemini** is the family of models (the "engine"), and **AI Studio** is the web-based interface that lets us experiment and prototype with that engine.

In this course, you'll use these professional-grade tools to build your applications, giving you direct experience with the same technology that powers major global companies.

## GitHub
**Your Project's Digital Headquarters 🏛️**

GitHub is far more than just a place to store code. It's a multifaceted platform that will serve as the entire headquarters for your team project. It has four key functions:

* **The Vault & Bookkeeper:** At its core, a GitHub **Repository** is a secure, cloud-based location for all your project's files (code, documents, images). It keeps a complete history of every change, so you can never lose your work.
* **The Meeting Room (Collaboration):** GitHub is where your team communicates. You'll use **comments on Issues and code**, **Discussion boards**, and **Wikis** to have transparent, documented conversations, ensuring everyone is on the same page.
* **The Control Room (Project Management):** This is where you manage your work. You'll use **Issues** to define tasks and **Projects** (Kanban boards) to track their progress from "To Do" to "Done."
* **The Workshop (Infrastructure):** This is where the actual work gets done. You'll use powerful, integrated tools like **GitHub Codespaces** (your cloud-based computer) and **GitHub Secrets** (a secure vault for passwords and API keys).

Mastering this platform is a highly valuable professional skill. A well-managed GitHub repository is one of the most powerful items you can have in your portfolio to demonstrate your technical and project management abilities to employers.

## **API Keys**
**The Secure Keys to the Digital Kingdom 🔑**

You will soon create and use an API key. It's crucial to understand what it is and why it must be protected. An API key is like a combination of a **secure password and a credit card** for the digital world.

* **What is it?** It's a unique, secret string of characters that you send along with any request to an AI model provider (like Google, OpenAI, or Anthropic).
* **Why is it required?**
    1.  **Authentication (It's your password):** It proves to the service that you are who you say you are and that you have permission to use their powerful AI models.
    2.  **Billing & Tracking (It's your credit card):** It's how these companies track your usage. In the real world, this usage is tied to the key for billing. (In this course, we will stay within free limits).
* **Why must it be kept SECRET?** If someone else gets your API key, they can use the AI service on your account. This is why we will **never** paste a key directly into our code. Instead, we will use professional tools like **GitHub Secrets** and **Colab Secrets** to store them securely.

## A Step-by-Step Guide

### **:material-numeric-1-circle: Get Your GitHub Account**

Before we begin, ensure you have a GitHub account. This single account is your passport to a professional suite of collaboration tools we will use all semester, including repositories, project boards, and our cloud-based coding environment, Codespaces.

### **:material-numeric-2-circle: Create Your Personal Setup Repository**

For this initial setup exercise, **each student will create their own individual repository** from the course template. This is to ensure everyone completes the setup process and that API keys are kept secure and private. You will create a separate, shared *team* repository later in the course.

1.  **Navigate to the Template:** Go to the template repository: `https://github.com/genaiforbusiness/chatbox`.
2.  **Create Your Repository:** Click "**Use this template**" to create a new repository.
3.  **Configure Your New Repository:**
    * **Owner:** Ensure the repository is owned by your personal GitHub account.
    * **Repository name:** Use the format `dev-setup-<your-github-username>` (e.g., `dev-setup-j-doe`).
    * **Visibility:** You **must** select **Private**.
4.  **Add the Instructor:** You must add the instructor as a collaborator so your setup can be verified. Go to **Settings > Collaborators and teams**, and invite the instructor using the username **`midhubalan`**.

### **:material-numeric-3-circle: Get & Secure API Key**

An API key is a secret password that allows your application to communicate with Google's AI models. This is a critical step that requires careful attention.

1.  **Understand the Process:** First, read the official Google documentation on how to [get an API key](https://ai.google.dev/gemini-api/docs/api-key). This guide explains the process you are about to follow.
2.  **Generate Your Key:** Go to [Google AI Studio](https://aistudio.google.com/apikey) and follow the steps to create your API key.
3.  **⚠️ Save Your Key Immediately:** The API key is only shown to you once. **Copy the key immediately** and paste it into a temporary, secure location. If you lose it before saving it in the next steps, you will need to create a new one.

### **:material-numeric-4-circle: Configure and Test GitHub Codespaces**

Now, we will securely store your key in your project's primary development environment.

1.  **Understand Secrets:** First, read the official GitHub documentation on [managing secrets for your Codespaces](https://docs.github.com/en/codespaces/managing-your-codespaces/managing-encrypted-secrets-for-your-codespaces).
2.  **Store the Secret:** In your team's GitHub repository, navigate to **Settings \> Secrets and variables \> Codespaces**. Create a **new repository secret** with the name `GOOGLE_API_KEY` and paste your API key as the value.
3.  **Launch and Test:**
      * Create a new Codespace on your `main` branch.
      * Once the environment is running, **follow the instructions in the `README.md` file** to run a test script. This will confirm that your Codespace can securely access the API key and communicate with the Gemini API.

!!! tip "**Custom GitHub Codespace Specification 💡**"

    
    The **GitHub Codespace** you launch for this course isn't a generic environment; it's a custom-built workspace specifically for our project, defined by a `devcontainer` specification in your repository.

    Think of it as a virtual computer where we've already installed all the special tools and files you'll need, so you can start building right away without worrying about setup.

    Key customizations pre-loaded for you include:

    * **[UV](https://docs.astral.sh/uv/):** A modern, high-speed Python package installer and resolver.
    * **[Gemini CLI](https://google-gemini.github.io/gemini-cli/):** A command-line interface for interacting directly with the Gemini family of models.
    * **[A Starter Streamlit App](https://docs.streamlit.io/):** A barebones application with the Google Gemini SDK already included as a dependency, giving you a ready-made foundation for your project.

### **:material-numeric-5-circle: Configure and Test Google Colab**

Finally, we will configure the environment used for our individual labs.

1.  **Understand Colab Secrets:** First, read the official Colab documentation on its [Secrets feature](https://colab.research.google.com/notebooks/relnotes.ipynb#scrollTo=eaf6a2fc&line=1&uniqifier=1).
2.  **Open the Test Notebook:** Open the [`gemini.ipynb`](https://colab.research.google.com/github/genaiforbusiness/code-samples/blob/main/gemini.ipynb) in Colab. 
3.  **Store the Secret:** In the notebook's side panel, click the **key icon (🔑)** to open the "Secrets" tab. Create a new secret with the name `GOOGLE_API_KEY` and paste your API key as the value. Ensure notebook access is enabled.
4.  **Run the Cells:** Execute the pre-populated code cells in the notebook. A successful run will confirm your Colab environment is also correctly configured.

