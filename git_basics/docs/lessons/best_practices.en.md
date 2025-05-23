# 🤝 Collaboration Best Practices

Working together on code can be super fun — and a little tricky if you’re just starting out. Here are some simple tips to make collaborating easier, cleaner, and less stressful. 🚀

---

## 🧠 1. Talk Before You Code

Communication is key! Before diving into work:

- Chat with your partner or team about what each of you is doing.
- Decide who’s doing what so you **don’t accidentally work on the same file** at the same time.
- Use messaging apps, a shared doc, or even just talk in person if you can. ☎️

---

## 🌱 2. Pull Before You Push

Before you push your changes to GitHub, run this in your terminal:

→ **Run in terminal:**

```bash
git pull
```

✅ This helps you grab the latest changes from your team.

📛 **If you don’t pull first, you might cause a merge conflict.**

---

## 🎯 3. Commit Often, With Clear Messages

Make small commits as you go and write short, helpful messages like:

→ **Run in terminal:**

```bash
    git commit -m "Add function to calculate average"
```

❌ Avoid messages like:

```bash
git commit -m "stuff"
git commit -m "fixed it"
```

✅ Good messages help your teammates understand what you did at a glance.

---

## 🧼 4. Clean Your Code Before Sharing

🧹 Before pushing to GitHub:

- Remove `print()` statements (unless they’re needed)
- Make sure your code **runs without errors**
- Use meaningful variable names (`total_price`, not `x`)

Your teammates will thank you! 🙏

---

## 🧪 5. Review Changes Together

Before merging your code:

- **Read over your changes** to catch mistakes
- **Ask your partner to review** (use GitHub pull requests if possible)

👀 Two pairs of eyes > one.

---

## 🔄 6. Resolve Conflicts Together

If a **merge conflict** happens:

- Don't panic 😅
- Open the file and look for lines like:

```bash
<<<<<<< HEAD
your changes
=======
their changes
>>>>>>> origin/main
```

- Talk with your teammate about which version to keep
- Edit the file to keep the correct version

Then:

→ **Run in terminal:**

```bash
git add .
git commit -m "Resolve conflict in file.py"
git push
```

---

## 🎉 8. Celebrate Wins

Finished a feature? Fixed a bug? Solved a tricky conflict?

🎉 High-five your teammate — remote or IRL!  
Small wins deserve recognition. It keeps teamwork fun. 🙌

---

## 🧭 9. Ask for Help (and Be Nice When Giving It)

It’s totally OK to ask questions. We’re all learning. 💬

And when someone asks you for help — be kind, patient, and encouraging.

We all started somewhere. 🤗