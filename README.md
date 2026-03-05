# Building and Publishing a Pelican Static Website Using Markdown
This README explains how to format and host a resume as a static website using Markdown, Pelican, Git, and GitHub Pages. It is intended for users who have no prior experience with Git, static site generators, or forges but who have a basic understanding of Markdown syntax.<br>

This document has two primary goals. First, it provides clear, structured, step-by-step instructions for installing the necessary tools, generating a static website locally, and publishing it online using GitHub Pages. Second, it connects these practical steps to key principles from Andrew Etter’s *Modern Technical Writing*, demonstrating how modern documentation tools promote clarity, maintainability, and accessibility.<br>

By following these instructions, you will be able to install Pelican, generate a static website from Markdown content, and publish that site online using a forge.

## Prerequisites
Before beginning, ensure that you have the following:
- [Visual Studio Code](https://code.visualstudio.com/download) (or another text editor)
- [A GitHub account](https://github.com/)
- Basic familiarity with command-line navigation
- Basic knowledge of Markdown (A tutorial could be found [here](https://www.markdowntutorial.com/)!)

## Instructions
The following are step-by-step instructions to help you get your site upp and running.

### Step 1: Install Python
1. Open a web browser and navigate to the [python download site](https://www.python.org/downloads/)
2. Download the installer for your operatign system
3. Run the installer and accept the default settings
4. Open a terminal
5. Type the following:

    ```
    python --version
    ```
6. Confirm that the version displayed is 3.10 or higher

### Step 2: Install Git
Etter encourages using distributed version control systems like Git to help ease collaboration and to ensure synchronization of code and documentation. By installing Git before beginning this process, you ensure that your content can be versioned, backed up, and published consistently.

1. Navigate to the [git install site](https://git-scm.com/install/)
2. Download the installer for your operating ssytem
3. Run the installer using the default settings
4. Open a terminal
5. Type the following:

    ```
    git --version
    ```
6. Confirm that Git is installed successfully.

### Step 3: Create a GitHub Repository
1. Log in to your GitHub account. If you do not have one, create one
2. Click "New repository."
3. Enter a repository name
4. Click "Create repository."

### Step 4: Clone the Repository
1. Copy the repository URL from GitHub.
2. Open Visual Studio Code.
3. Open the terminal inside VS Code.
4. Navigate to your desired directory.
5. Type the following:
   
    ```
    git clone [repository URL].
    ```
6. Press Enter.
7. Open the cloned folder in VS Code.

### Step 5: Create a Virtual Environment
1. In the terminal in VS Code, type the following:
   
    ```
    python -m venv .venv
    ```
2. Press Enter
3. Type the following (for windows):

    ```
    .\.venv\Scripts\activate
    ```
4. Press Enter

### Step 6: Install Pelican
1. Type the following in the VS Code terminal:
   
   ```
   python -m pip install "pelican[markdown]"
   ```
2. Press Enter
3. Type the following:
   
   ```
   pelican --version
   ```
4. Confirm that Pelican is installed

Pelican is a ststic site generator. According to Etter, static site generators offer speed, simplicity, and ease of hosting. This makes documentation easier to deploy and maintain.

### Step 7: Initialize a Pelican Project
1. Type the following in the VS Code terminal:
   
   ```
   pelican-quickstart
   ```
2. Press Enter.
3. Answer the configuration prompts.

### Step 8: Add Resume Content in Markdown
1. Navigate to the **content** folder in the project directory in VS Code.
2. Create a new file names **resume.md**.
3. Add Markdown-formatted resume content.
4. Save the file

Markdown provides a lightweight syntax. Andrew Etter advocates for its simplicity and popularity stating that various "flavours" exist.

### Step 9: Generate the Website Locally
1. In the VS Code terminal, type the following:
   
   ```
   pelican content
   ```
2. Press Enter
3. Type the following:
   
   ```
   pelican --listen
   ```
4. Press Enter
5. Open the displayed local URL in your browser

### Step 10: Publish to GitHub Pages
1. Type the following in the VS Code terminal:
   
   ```
   pelican content -s publishconf.py
   ```
2. Press Enter
3. Install ghp-import by typing:
   
   ```
   pip install ghp-import
   ```
4. Press Enter
5. Type the following:
   
   ```
   ghp-import output -b gh-pages
   ```
6. Press Enter
7. Type the following:
   
    ```
   git push origin gh-pages
   ```
8. Press Enter

Finally:
1. Open your GitHub repository
2. Click **Settings**
3. Click **Pages**
4. Select the *gh-pages* branch
5. Save the settings

GitHub will generate a public URL for your site.

In *Modern technical Writing*, we are told that static websites offer speed, simplicity, and ease of hosting which make it easy to run the website an dmakew it available for everyone. That is why we would be running this website.

## Further Resources/Readings
- [GitHub Pages Documentation](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site)
- [Pelican Site Publication](https://docs.getpelican.com/en/latest/publish.html#site-generation)
- [Markdown Live Guide](https://markdownlivepreview.com/)

## FAQ
**Why use Markdown instead of raw HTML?**<br>
*Markdown is simpler and more readable than raw HTML. Because it is lightweight, it reduces errors and improves collaboration. According to Etter, it offers simplicity but lacks a formal standard. It also has a cleaner syntax and allows for better maintainability.*<br>

**I updated my Markdown file, but the published website did not change. Why?**<br>
*You must regenerate and redeploy the site after making changes. Static site generators do not update automatically. Run **pelican content -s publishconf.py**, then republish using **ghp-import**. Additionally, GitHub Pages may take several minutes to redeploy. You can monitor deployment under the **“Actions”** tab. If changes still do not appear, clear your browser cache and hard reload the page.*

**Why is the README in the same repository as the static website code?**<br>
*Keeping the README in the same repository as the website source code ensures that the documentation and the project remain synchronized. When documentation is stored alongside the code it describes, updates to the project can be documented immediately, reducing the risk that instructions become outdated. Andrew Etter emphasizes that modern technical documentation should live with the source code rather than in a separate system. This approach encourages collaboration because contributors only need to access a single repository to view both the code and its documentation. It also improves efficiency for users and developers, since all necessary materials for understanding and maintaining the project are available in one place.*


## Credits
This webiste was developed using Pelican and was hosted using GitHub Pages.

Other sources of content used are:
- [Overleaf Resume Template](https://www.overleaf.com/latex/templates/mbzuai-resume-template/xfqbdzbfdkkf.pdf)
- [README Template](https://github.com/PurpleBooth/a-good-readme-template)

Peer Review Contributors (Megaminds Group):<br>
- Chinyere Ajufoh-Obi
- Paul Watuwa
