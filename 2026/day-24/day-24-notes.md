# Day 24 – Advanced Git: Merge, Rebase, Stash & Cherry Pick

## Task


---

## Challenge Tasks

### Task 1: Git Merge — Hands-On
1. Create a new branch `feature-login` from `main`, add a couple of commits to it
![alt text](image.png)
2. Switch back to `main` and merge `feature-login` into `main`
![alt text](image-1.png)
3. Observe the merge — did Git do a **fast-forward** merge or a **merge commit**?

![alt text](image-2.png)
4. Now create another branch `feature-signup`, add commits to it — but also add a commit to `main` before merging
![alt text](image-3.png)
5. Merge `feature-signup` into `main` — what happens this time?
![alt text](image-4.png)

before merge to main log : ![alt text](image-5.png)
after merge main log looks like this: ![alt text](image-6.png)
6. Answer in your notes:
   - What is a fast-forward merge?
   - When does Git create a merge commit instead?
   - What is a merge conflict? (try creating one intentionally by editing the same line in both branches)

---

### Task 2: Git Rebase — Hands-On
1. Create a branch `feature-dashboard` from `main`, add 2-3 commits
2. While on `main`, add a new commit (so `main` moves ahead)
3. Switch to `feature-dashboard` and rebase it onto `main`
4. Observe your `git log --oneline --graph --all` — how does the history look compared to a merge?
5. Answer in your notes:
   - What does rebase actually do to your commits?
   - How is the history different from a merge?
   - Why should you **never rebase commits that have been pushed and shared** with others?
   - When would you use rebase vs merge?

---

### Task 3: Squash Commit vs Merge Commit
1. Create a branch `feature-profile`, add 4-5 small commits (typo fix, formatting, etc.)

![alt text](image-7.png)
2. Merge it into `main` using `--squash` — what happens?
differnece : ![alt text](image-8.png)
git merage --squash feature-profile: ![alt text](image-9.png)
after merge: ![alt text](image-10.png)
commit structure is clean all commmits of feature-p branch got merge into into one.
3. Check `git log` — how many commits were added to `main`?:  One
4. Now create another branch `feature-settings`, add a few commits
![alt text](image-11.png)
5. Merge it into `main` **without** `--squash` (regular merge) — compare the history
before merge: ![alt text](image-12.png)
regular merge message: ![alt text](image-13.png)
after merge main log: ![alt text](image-14.png)

6. Answer in your notes:
   - What does squash merging do? commit structure is clean all commmits of feature-p branch got merge into into one.
   - When would you use squash merge vs regular merge? for clean commit history use squash merge and for all commit history use regular merge
   - What is the trade-off of squashing?
   
   Trade-offs (What You Lose)

 Loss of Granular History
- Individual commits (bug fixes, experiments, progress) are gone

 Harder Debugging
- You can’t easily pinpoint which exact commit introduced a bug

Reduced Traceability
- Less visibility into development process (who did what, step-by-step)

Collaboration Issues (Sometimes)
- If others depend on commit history, rewriting it (via rebase + squash) can cause conflicts
---

### Task 4: Git Stash — Hands-On
1. Start making changes to a file but **do not commit**
![alt text](image-15.png)
![alt text](image-16.png)
![alt text](image-17.png)
2. Now imagine you need to urgently switch to another branch — try switching. What happens?

3. Use `git stash` to save your work-in-progress
4. Switch to another branch, do some work, switch back
![alt text](image-18.png)
5. Apply your stashed changes using `git stash pop`
![alt text](image-19.png)
6. Try stashing multiple times and list all stashes
![alt text](image-20.png)
7. Try applying a specific stash from the list
from man git stash
       ``` 
       git stash list [<log-options>]
       git stash show [-u | --include-untracked | --only-untracked] [<diff-options>] [<stash>]
       git stash drop [-q | --quiet] [<stash>]
       git stash pop [--index] [-q | --quiet] [<stash>]
       ```
![alt text](image-21.png)
8. Answer in your notes:
   - What is the difference between `git stash pop` and `git stash apply`?
   - When would you use stash in a real-world workflow?
   - git stash apply
    
    Applies the stashed changes to your working directory

    Does NOT remove the stash from the stash list

    ✅ Use when:

    You may need the same stash again

    You want a backup safety
    ![alt text](image-23.png)

   - git stash pop

    Applies the stashed changes

    REMOVES the stash from the stash list after applying

    ✅ Use when:

    You are sure you don’t need the stash anymore

    You want to keep stash list clean
    ![alt text](image-22.png)

---

### Task 5: Cherry Picking
1. Create a branch `feature-hotfix`, make 3 commits with different changes
![alt text](image-24.png)
2. Switch to `main`
currect main log: ![alt text](image-25.png)

3. Cherry-pick **only the second commit** from `feature-hotfix` onto `main`
![alt text](image-26.png)
4. Verify with `git log` that only that one commit was applied
![alt text](image-27.png)
5. Answer in your notes:
   - What does cherry-pick do? picking the required commit in your branch.
   - When would you use cherry-pick in a real project? to avoid bug free working code and cleaner commit history for tracking
   - What can go wrong with cherry-picking?
   Merge conflicts if branches have diverged, duplicate commits in history, missing dependencies that break code, loss of context for changes, and overall confusing project history.

---

## Hints
- Visualize history: `git log --oneline --graph --all`
- To intentionally create a merge conflict: edit the **same line** of the **same file** on two branches
- Stash with a message: `git stash push -m "description"`
- Cherry-pick needs a commit hash — find it with `git log --oneline`

---

## Submission
1. Add your `day-24-notes.md` to `2026/day-24/`
2. Update `git-commands.md` with all new commands and commit
3. Push to your fork

---