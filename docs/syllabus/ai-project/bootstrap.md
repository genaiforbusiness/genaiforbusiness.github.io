---
icon: material/calendar-start-outline
---

# Project Bootstrap

## Team & Repository Setup

### Objective 🎯

<!-- :robot: 

:cloud_lightning:

:calendar:

:people_holding_hands_tone1: -->

The goal of this first task is to get your team organized and set up the professional collaboration environment we will use for the entire semester: **GitHub**. This exercise will ensure that every team member has a working GitHub account and understands the basic workflow of making a contribution to a shared project. We will use a course template that includes pre-configured settings for our development environment.

### Due Date & Grading

  * **Due:** See Canvas.
  * **Grading:** This is a **Complete / Incomplete** task that's an integral part of your project. To receive a "Complete" grade for this assignment, every team member must successfully complete their part.

-----

### Step-by-Step Instructions

#### **Step 1: Form Your Team**

Decide on your project team of 3-4 members. Once your team is formed, designate one person to be the "Repo Lead" for the initial setup.

#### **Step 2: Create the Repository from Template (Repo Lead's Task)**

The Repo Lead will create the shared project space by using a course template.

1.  **Navigate to the Template:** Go to the template repository at [https://github.com/genaiforbusiness/chatbox](https://github.com/genaiforbusiness/chatbox).
2.  **Use the Template:** Click the green "**Use this template**" button and select "**Create a new repository**".
3.  **Configure Your New Repository:**
      * **Owner:** Ensure the repository is owned by your personal GitHub account.
      * **Repository name:** Use the format `ai-poc-team-<your-team-name>` (e.g., `ai-poc-team-innovators`).
      * **Visibility:** You **must** select **Private**. This is a critical step.
      * Click "**Create repository**".
4.  **Add Collaborators:** Add Collaborators: In your newly created repository, go to Settings > Collaborators and teams. You must add two types of collaborators:
    - **Your Teammates**: Click "Add people" and add each of your teammates using their GitHub username.
    - **The Instructor**: You must also add the instructor so your work can be viewed and graded. The instructor's GitHub username is `midhubalan`.

Your teammates and the instructor will need to accept the email invitation to gain access. This step is critical for grading.

#### **Step 3: Clone the Repository (Everyone's Task)**

Now, each team member needs to create a local copy of the project on their computer (or in their Codespace).

1.  Navigate to the main page of the **team's new repository** (not the template).
2.  Click the green "**<\> Code**" button.
3.  Copy the URL provided (use the HTTPS option).
4.  Open a terminal or command prompt and run the following command:
    ```bash
    git clone <paste-the-repository-url-here>
    ```

#### **Step 4: Create Your Profile Page (Everyone's Task)**

This is your first individual contribution to the project.

1.  Navigate into the new project folder you just cloned.
2.  Create a new file. The filename **must be** your exact GitHub username followed by `.md`. For example, if your username is `j-doe`, the file must be named `j-doe.md`.
3.  Open the file and add the following information using Markdown formatting:
    ```markdown
    # [Your Name]

    **Major:** [Your Major]

    **What I want to learn in this course:** [A brief sentence about your goals]

    **A fun fact about me:** [Something interesting!]
    ```
4.  Save the file.

#### **Step 5: Commit and Push Your Changes (Everyone's Task)**

Finally, you will save your new file to the shared repository on GitHub using a three-step command-line process.

1.  **Add the file:** Tell Git to track your new file.
    ```bash
    git add <your-github-username>.md
    ```
2.  **Commit the file:** Save a snapshot of your changes with a descriptive message.
    ```bash
    git commit -m "feat: Add profile for <your-github-username>"
    ```
3.  **Push the file:** Send your saved changes up to the shared GitHub repository.
    ```bash
    git push
    ```

-----

### Submission & Verification

  * **Submission:** The **Repo Lead** will submit a single link to the team's GitHub repository on [Canvas](https://canvas.pitt.edu/courses/320955).
  * **Verification:** Before submitting, check the following:
      * ✅ The repository is **private**.
      * ✅ All team members are listed as **collaborators** under Settings.
      * ✅ Each team member has successfully created and pushed their own unique `<username>.md` file to the repository.
      * ✅ All team members appear under the "**Contributors**" tab on the main repository page.