# Day 10 – File Permissions & File Operations Challenge

## Task

---


## Challenge Tasks

### Task 1: Create Files (10 minutes)

1. Create empty file `devops.txt` using `touch`
2. Create `notes.txt` with some content using `cat` or `echo`
![alt text]({6C77C629-C9A5-4D57-8A9C-8AE7ABBE2D1F}.png)
3. Create `script.sh` using `vim` with content: `echo "Hello DevOps"`
![alt text]({064F818B-1F70-4130-AFE0-CA1AF917E13A}.png)
**Verify:** `ls -l` to see permissions
![alt text]({C570085F-A7C7-4D1D-88B6-CF1225294B76}.png)
---

### Task 2: Read Files (10 minutes)

1. Read `notes.txt` using `cat`
2. View `script.sh` in vim read-only mode
3. Display first 5 lines of `/etc/passwd` using `head`
![alt text]({4EC17093-59CF-4AAB-887A-1B089E92DE36}.png)
4. Display last 5 lines of `/etc/passwd` using `tail`
![alt text]({9DE1F8BF-3C76-4A4D-8164-E8FDEB5EF35C}.png)

---

### Task 3: Understand Permissions (10 minutes)

Format: `rwxrwxrwx` (owner-group-others)
- `r` = read (4), `w` = write (2), `x` = execute (1)

Check your files: `ls -l devops.txt notes.txt script.sh`
![alt text]({43BF52BF-A6E5-4B8A-8020-D3B38DD6D023}.png)

Answer: What are current permissions? Who can read/write/execute?

---

### Task 4: Modify Permissions (20 minutes)

1. Make `script.sh` executable → run it with `./script.sh`
![alt text]({C23879B8-639B-4E53-991E-DF7FC2FB3D5A}.png)

![alt text]({FC97A3D0-C4C4-4531-99C9-D58AD95F25B0}.png)
2. Set `devops.txt` to read-only (remove write for all)
![alt text]({071CB2A4-CED1-44DE-9951-F058AF581895}.png)
3. Set `notes.txt` to `640` (owner: rw, group: r, others: none)
![alt text]({AD538765-0934-46E9-8898-DD994D5FBA4E}.png)
4. Create directory `project/` with permissions `755`
![alt text]({45DB9C4F-D5EE-4644-B66E-AFF9B855A1D5}.png)
**Verify:** `ls -l` after each change

---

### Task 5: Test Permissions (10 minutes)

1. Try writing to a read-only file - what happens?
![alt text]({7EB5755C-11DE-4B43-9D6F-62283AF98A39}.png)
2. Try executing a file without execute permission
![alt text]({A936217F-D916-42FF-BEBE-ECBDD22D434E}.png)
3. Document the error messages

---