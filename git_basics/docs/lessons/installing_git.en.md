# 🛠️ How to Install Git and Use GitHub

Hey there! 👋 Let’s get Git set up on your computer and connect it to GitHub. It’s easier than you think — just follow the steps below!

---

## 💻 Installing Git on Your Computer

Pick your operating system below to see the right instructions 👇

=== "🪟 Windows"

    1. Go to [https://git-scm.com/download/win](https://git-scm.com/download/win)
    2. Download the file and run it.
    3. Click “Next” through the setup — the default settings are perfect.
    4. Done. 🎉

=== "🍏 Mac"

    1. Open the **Terminal** app (search for "Terminal").
    2. Type this and press Enter:  
       `git --version`
    3. If it says Git is not installed, type:  
       `xcode-select --install`
    4. Follow the instructions that pop up. ✅

=== "🐧 Linux (Ubuntu)"

    1. Open **Terminal**.
    2. Type the following commands one at a time and press Enter:  

       ```
       sudo apt-get update
       sudo apt-get install git
       ```
    3. All done! Git is installed and ready. 💪

---

## ✍️ Set Up Git with Your Name

Once Git is installed, open Git Bash or Terminal and tell Git who you are:

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

## 🌐 What is GitHub?

GitHub is a free website where you can:

- 🗃️ Store your projects online
- 👯 Collaborate with others
- 📣 Show your work to the world!

## 🚀 How to Use GitHub

- Go to [https://github.com](https://github.com) and **sign up for a free account**.

![GitHub SignUp](imgs/github_signup.png)

- In the top-right corner, click the **+** icon and choose **New repository**.

![GitHub New Repository](imgs/github_new_repo.png)

- Give your project a name (like `my-first-project`) and click **Create repository**.

![GitHub Create Repository](imgs/github_create_repo.png)

Git has many other options, for now the ones that could be important are:

    - Public repository: The repository is visible to anyone. Use this for projects you want to share with many people.
    - Private repository: The repository is visible to you and the people yoi invite only. Use this for private projects, where you want to protect your code.

- After it's created, copy the web address (also called the **URL**) that looks something like: `https://github.com/your-username/your-repo-name.git`.

![GitHub Link](imgs/github_link.png)

- Now open the **Terminal** and type this command to copy the project to your computer:

```bash
git clone [https://github.com/your-username/your-repo-name.git]
```

- Press Enter and Git will download the project folder to your computer. 🎉