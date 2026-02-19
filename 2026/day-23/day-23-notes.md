# Day 23 – Git Branching & Working with GitHub

## Task
---

## Challenge Tasks

### Task 1: Understanding Branches
Answer these in your `day-23-notes.md`:
1. What is a branch in Git? parallel copy of your current timeline where you can do modification without hurting main branch
2. Why do we use branches instead of committing everything to `main`? In production we have usually have main(which is production which is serving customers), dev(Copy of main to do the development work), staggging (backup branch of main where you test you new changes just one step earlier you push or merge the branch with main branch), test or feature(where you do the testing and new features research)
3. What is `HEAD` in Git? tells the latest changes in branch
4. What happens to your files when you switch branches? Your changes branch right after modifying a file changes will show in other branch 

---

### Task 2: Branching Commands — Hands-On
In your `devops-git-practice` repo, perform the following:
1. List all branches in your repo
2. Create a new branch called `feature-1`
3. Switch to `feature-1`
4. Create a new branch and switch to it in a single command — call it `feature-2`
5. Try using `git switch` to move between branches — how is it different from `git checkout`?
6. Make a commit on `feature-1` that does **not** exist on `main`
7. Switch back to `main` — verify that the commit from `feature-1` is not there
8. Delete a branch you no longer need
9. Add all branching commands to your `git-commands.md`
![alt text](image.png)

---

### Task 3: Push to GitHub
1. Create a **new repository** on GitHub (do NOT initialize it with a README)
2. Connect your local `devops-git-practice` repo to the GitHub remote
3. Push your `main` branch to GitHub
4. Push `feature-1` branch to GitHub
5. Verify both branches are visible on GitHub
6. Answer in your notes: What is the difference between `origin` and `upstream`?
Feature What is it?		

- origin: Your fork / Your personal copy	
- upstream: The original, main project

![alt text](image-1.png)
---

### Task 4: Pull from GitHub
1. Make a change to a file **directly on GitHub** (use the GitHub editor)
2. Pull that change to your local repo
3. Answer in your notes: What is the difference between `git fetch` and `git pull`?
![alt text](image-2.png)
---

### Task 5: Clone vs Fork
1. **Clone** any public repository from GitHub to your local machine 

2. **Fork** the same repository on GitHub, then clone your fork
3. Answer in your notes:
   - What is the difference between clone and fork?
   clone is copying the remote repo on local machine

   fork copy of remote repo on your gh repo (no write access to original repo)
   - When would you clone vs fork?
   for working localing use clone

   No write access: You want to contribute to a public open-source project.
   Experimentation: You want to make changes or experiment without affecting the original project.

   for 
   - After forking, how do you keep your fork in sync with the original repo?
   by selecing option sync fork(which work on ff concept fast forward )
![alt text](image-3.png)

---

## Hints
- When you create a branch, it starts from the commit you're currently on
- `git switch` is the modern alternative to `git checkout` for switching branches
- To push a new branch: `git push -u origin <branch-name>`
- A fork is a GitHub concept, not a Git concept

---