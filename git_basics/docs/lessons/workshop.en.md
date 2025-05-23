# 🧪 Git & GitHub Paired Exercise: Python Functions and Version Control

This tutorial will guide you and a partner through collaborating on a Python project using Git and GitHub. You’ll practice creating a repo, cloning it, writing code, committing changes, pushing to GitHub, and resolving a merge conflict.

---

## 📁 Step 0: Create a GitHub Repository

Partner A should:

1. Go to https://github.com and log into your account.
2. Click the **+** icon in the top right, then choose **New repository**.
3. Name the repository: `python-functions-practice`
4. Optionally, add a description.
5. **Leave all checkboxes unchecked** (no README, no .gitignore, no license).
6. Click **Create repository**.
7. Copy the HTTPS URL shown (you’ll use it to clone).

---

## 👫 Step 1: Invite Your Partner to the Repository

Still Partner A:

1. Go to the repository page on GitHub.
2. Click the **Settings** tab.
3. Under **Access**, click **Collaborators**.
4. Click **Invite a collaborator**.
5. Type your partner’s GitHub username and send the invite.

Partner B must accept the invitation before continuing.

---

## 💻 Step 2: Clone the Repository

Now **both partners** should run this at the same time:

→ Run in terminal:

```bash
git clone https://github.com/[your-username]/python-functions-practice.git
cd python-functions-practice
```

---

## 🐍 Step 3: Partner A - Create a Python File

Partner A: create a file named `math_utils.py`, and define a function that calculates the summation from 1 to <code>n</code>. Before showing the right answer, try to do it!

??? example "Answer"

    ```python
    def summation(n):
        summation = 0
        for i in range(n + 1):
            summation += i
        return summation
    ```

Now that you’ve created your file, let’s see what Git thinks is happening. Try to run a status with git. Do you remember how to do it?

??? example "Answer"

    → Run in terminal:

    ```bash
    git status
    ```
    
    What do you see? Probably, your output looks like this:
    
    <span style="color:red">math_utils.py</span>

    This means that the file is `untracked`. That is, we have made some changed in the file, but it won’t be included in the next commit unless you git add it.
    
Let's try to add it! Do a git add, but don't see the answer until you try it:

??? example "Answer"

    → Run in terminal:

    ```bash
    git add math_utils.py
    ```

Now, we have placed added the `math_utils.py`. But still, we need to make a commit. Try to do a commit with the message "Added summation function".

??? example "Answer"

    → Run in terminal:

    ```bash
    git commit -m "Add summation function"
    ```

Great! Try to check the `GitHub` repository you just created.

Hmmm... There is nothing there... Are we missing something?

??? example "Answer"

    Correct! We need to do a `push` to send those changes into the remote repository.

    → Run in terminal:

    ```bash
    git push
    ```

    Try to see your GitHub repository to check that the file is there.

---

## 👥 Step 4: Partner B - Add a New Function

Partner B: create a file named `math_utils.py`, and define a function that calculates the summation from 1 to <code>n</code>. It has to be a different implementation. Before showing the right answer, try to do it!

??? example "Answer"

    ```python
    def summation(n):
        return sum(range(1, n + 1))
    ```

Good! Now, try to do the same as your partner. Try to push the changes into the remote repository.

??? example "Answer"

    → Run in terminal:

    ```bash
    git add math_utils.py
    git commit -m "Added a mean function"
    git push
    ```

Whoops... Something went wrong... What is it?

??? example "Answer"

    Partner B did a change in a file that was already created, but the remote file has some changes that Partner B does not have on its local machine.

    This is known as a `conflict`. It happens when you do changes locally but you did not pull the changes that other people did in the remote repository.


---

## 🚨 Step 5: Expect a Merge Conflict

Partner B: are likely seeing something like

<span style="color:red">! [rejected] main -> main (fetch first)</span>

This means someone else (Partner A) already pushed changes.

→ Run in terminal:

```bash
git pull --no-rebase
```

You’ll see a merge conflict in `math_utils.py`.

---

## 🛠️ Step 6: Resolve the Merge Conflict

Open `math_utils.py`. You’ll see something like:

```python
<<<<<<< HEAD
def summation(n):
    return sum(range(1, n + 1))
=======
def summation(n):
    summation = 0
    for i in range(n + 1):
        summation += i
    return summation
>>>>>>> main
```

On top, you will see some options, such as `Accept Current Change` | `Accept Incoming Change` | `Accept Both Changes` | `Compare Changes`.

These are some alternatives that you can choose to solve the conflict. They mean:

- Accept Current Change
→ Keeps your local changes and discards the remote ones.

- Accept Incoming Change
→ Keeps the changes from the remote repository and discards your local edits.

- Accept Both Changes
→ Includes both your changes and the remote changes, stacked one after the other.
⚠️ You’ll often need to edit manually afterward to make the result make sense.

- Compare Changes
→ Shows a side-by-side diff view to help you decide which changes to keep.

Let's try to accept both changes. If the file made something weird, try to change it so it looks like this:

```python
def summation(n):
    return sum(range(1, n + 1))

def summation_2(n):
    summation = 0
    for i in range(n + 1):
        summation += i
    return summation
```

Then run:

→ Run in terminal:
```bash
git add math_utils.py
git commit -m "Resolve merge conflict and keep both functions"
git push
```

---

# 🧪 Bonus lesson: VSCode Git & GitHub Paired Exercise

Try to recreate the tutorial inverting your roles. But now, we will try to use the Built-In feature of Visual Studio Code to manage the git repository. Instead of using bash git commands, we can use VS Code to do everything we need.

If you need some help, check the [VS Code Git](commands_vs_code.en.md) section.

---

## 💬 Pro Tips

- Run `git status` often — it's your guide to what's happening.
- Communicate with your partner to avoid overlap and confusion.
- Always pull before pushing when working in teams.

Happy coding!