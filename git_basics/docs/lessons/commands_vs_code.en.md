# Basic Git Commands You Need to Know in Visual Studio Code

In Visual Studio Code, there is a Built-In feature to manage your git repository. IN the left side of your VS Code window, you will see this symbol:

![VS Code Git Symbol](imgs/vs_git.png)

Click on it to use the graphical interface.

## `git add`

This command tells Git which files you want to include in the next snapshot (commit).

To add all files, click the `+` symbol in the changes section:

![VS Code Git Add All](imgs/vs_git_add_all.png)

To add a specific file, click the `+` symbol in the file you want to add:

![VS Code Git Add](imgs/vs_git_add.png)

You will see your added files in the `Staged Changes` section:

![VS Code Staged](imgs/vs_git_staged.png)

---

## `git commit`

This command saves the changes you've added, along with a message describing what you did.

You can set your message in the `message` box. When you are ready, just press the `commit` button:

![VS Code Commit](imgs/vs_git_commit.png)

---

## `git status`

This command is not available through VS Code. Yu can see the state of each file with the UI, seeing if the files are `Staged`. If you see no files in the git section, then you have made no changes to those files.

---

## `git push`

This command sends your committed changes to a remote repository like GitHub.

To run this, just press the `Sync Changes` button:

![VS Code Push](imgs/vs_git_push.png)

To see these commands in terminal, check the [Git Commands](commands.en.md).