# Day 28 – Revision Day: Everything from Day 1 to Day 27

## Task

You've covered a lot of ground in 27 days — DevOps fundamentals, Linux deep dives, Shell scripting, Python basics, Git & GitHub, and even your developer branding. Today, **stop and revise**. No new concepts. Just solidify what you've learned.

The goal is to identify gaps, revisit topics you struggled with, and make sure you can confidently explain and use everything covered so far.

---


## Task

You've covered a lot of ground in 27 days — DevOps fundamentals, Linux deep dives, Shell scripting, Python basics, Git & GitHub, and even your developer branding. Today, **stop and revise**. No new concepts. Just solidify what you've learned.

The goal is to identify gaps, revisit topics you struggled with, and make sure you can confidently explain and use everything covered so far.

---

## What You've Covered So Far

| Days | Topic | Key Concepts |
|------|-------|-------------|
| 1 | DevOps & Cloud Intro | What is DevOps, SDLC, Cloud basics |
| 2–7 | Linux Fundamentals | Architecture, commands, processes, systemd, file system hierarchy, troubleshooting, text files |
| 8 | Cloud Server Setup | Docker, Nginx, web deployment |
| 9–11 | Users, Permissions & Ownership | User/group management, file permissions, chown/chgrp |
| 12 | Revision Day 1 | Days 1–11 recap |
| 13 | Volume Management | LVM — physical volumes, volume groups, logical volumes |
| 14–15 | Networking | Fundamentals, DNS, IP, subnets, ports, hands-on checks |
| 16–18 | Shell Scripting | Basics, loops, arguments, error handling, functions |
| 19–20 | Shell Scripting Projects | Log rotation, backup, crontab, log analyzer |
| 21 | Shell Scripting Cheat Sheet | Personal reference guide |
| 22–25 | Git & GitHub | Init, branching, merge, rebase, stash, cherry pick, reset, revert, branching strategies |
| 26 | GitHub CLI | Managing GitHub from the terminal |
| 27 | GitHub Profile | Profile README, repo organization, developer branding |

---

## Challenge Tasks

### Task 1: Self-Assessment Checklist
Go through the checklist below. For each item, mark yourself honestly:
- **Can do confidently**
- **Need to revisit**
- **Haven't done yet**

#### Linux
- [ yes ] Navigate the file system, create/move/delete files and directories
- [ yes ] Manage processes — list, kill, background/foreground
- [  yes ] Work with systemd — start, stop, enable, check status of services
- [ yes ] Read and edit text files using vi/vim or nano
- [ yes ] Troubleshoot CPU, memory, and disk issues using top, free, df, du
- [ yes ] Explain the Linux file system hierarchy (/, /etc, /var, /home, /tmp, etc.)
- [ yes ] Create users and groups, manage passwords
- [ yes ] Set file permissions using chmod (numeric and symbolic)
- [ yes ] Change file ownership with chown and chgrp
- [ yes ] Create and manage LVM volumes
- [ yes ] Check network connectivity — ping, curl, netstat, ss, dig, nslookup
- [ yes ] Explain DNS resolution, IP addressing, subnets, and common ports

#### Shell Scripting
- [ yes ] Write a script with variables, arguments, and user input
- [ yes ] Use if/elif/else and case statements
- [ yes ] Write for, while, and until loops
- [ yes ] Define and call functions with arguments and return values
- [ yes ] Use grep, awk, sed, sort, uniq for text processing
- [ yes ] Handle errors with set -e, set -u, set -o pipefail, trap
- [ yes ] Schedule scripts with crontab

#### Git & GitHub
- [ yes ] Initialize a repo, stage, commit, and view history
- [ yes ] Create and switch branches
- [ yes ] Push to and pull from GitHub
- [ yes ] Explain clone vs fork
- [ yes ] Merge branches — understand fast-forward vs merge commit
- [ yes ] Rebase a branch and explain when to use it vs merge
- [ yes ] Use git stash and git stash pop
- [ yes ] Cherry-pick a commit from another branch
- [ yes ] Explain squash merge vs regular merge
- [ yes ] Use git reset (soft, mixed, hard) and git revert
- [ yes  ] Explain GitFlow, GitHub Flow, and Trunk-Based Development
- [ yes ] Use GitHub CLI to create repos, PRs, and issues

---

### Task 2: Revisit Your Weak Spots
1. Pick **3 topics** from the checklist where you marked "Need to revisit"
2. Go back to that day's challenge and redo the hands-on tasks
3. Document what you re-learned in `day-28-notes.md`

---

### Task 3: Quick-Fire Questions
Answer these from memory (no Googling). Then verify your answers:

1. What does `chmod 755 script.sh` do?
change permission to rwx rw rx rx
2. What is the difference between a process and a service?

process 

A process is simply a running instance of any program.

- Created when you run a command or app
- Has a PID (Process ID)
- Can be foreground or background
- Can start/stop anytime


service
A service is a special type of process that:

- Runs in the background (daemon)
- Usually starts at system boot
- Managed by tools like systemctl
- Provides system or application functionality

3. How do you find which process is using port 8080?

ss -tulpn | grep 8080

4. What does `set -euo pipefail` do in a shell script?

- e → Exit immediately if any command fails
- u → Treat unset variables as an error
- o pipefail → If any command in a pipeline fails, the whole pipeline fails

5. What is the difference between `git reset --hard` and `git revert`?
git reset --hard
- Moves the branch pointer to a previous commit
- Deletes commits from history (rewrites history)
- Also resets:
    staging area
    working directory

git revert
- Creates a new commit that undoes changes of a previous commit
- Does NOT delete history
- Safe for shared/public branches

# DevOps Cheatsheet (Git + Linux)

## 6. Branching Strategy (Team of 5, Weekly Releases)

**Recommended: Feature Branch + Main (Light GitFlow)**

* `main` → production-ready
* `develop` → integration (optional for small teams)
* `feature/*` → new features
* `release/*` → pre-release testing (optional)

**Why:**

* Parallel work
* Easy PR reviews
* Stable weekly releases

---

## 7. git stash

**What it does:**
Temporarily saves uncommitted changes without committing

```bash
git stash
git stash pop
```

**Use when:**

* Switching branches with unfinished work
* Pulling latest changes without committing

---

## 8. Schedule Script at 3 AM

Use **cron job**

```bash
crontab -e
```

Add:

```bash
0 3 * * * /path/to/script.sh
```

---

## 9. git fetch vs git pull

| Command   | Description                       |
| --------- | --------------------------------- |
| git fetch | Downloads changes only            |
| git pull  | Fetch + merge into current branch |

**Tip:**

* Use `fetch` → safer
* Use `pull` → quick update

---

## 10. LVM (Logical Volume Manager)

**What it is:**
Flexible disk management system in Linux

**Why use it:**

* Resize storage easily
* Combine multiple disks
* Take snapshots
* No downtime changes

**Vs Regular Partitions:**

* Fixed size ❌
* Dynamic & scalable ✅

---

---

### Task 4: Organize Your Work
1. Make sure all your daily submissions (day-1 through day-27) are committed and pushed
2. Check that your `git-commands.md` is up to date
3. Check that your shell scripting cheat sheet is complete
4. Verify your GitHub profile and repos are clean (from Day 27)

---

### Task 5: Teach It Back
Pick **one topic** you've learned and write a short explanation (5-10 lines) as if you're teaching it to someone who has never heard of it. Add it to your `day-28-notes.md`.

Examples:
- Explain Git branching to a non-developer
- Explain file permissions to a new Linux user
- Explain what a crontab is and why sysadmins use it

Teaching is the best test of understanding.

---

## Submission
1. Add your `day-28-notes.md` to `2026/day-28/`
2. Push to your fork
3. Make sure all previous days are pushed and up to date

---

## Learn in Public

Share your self-assessment results or your "teach it back" explanation on LinkedIn. Be honest about what you found easy and what you need to work on.

`#90DaysOfDevOps` `#DevOpsKaJosh` `#TrainWithShubham`

Happy Learning!
**TrainWithShubham**
