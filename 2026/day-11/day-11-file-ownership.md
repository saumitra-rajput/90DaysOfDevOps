# Day 11 – File Ownership Challenge (chown & chgrp)

## Task
---

## Challenge Tasks

### Task 1: Understanding Ownership (10 minutes)

1. Run `ls -l` in your home directory
2. Identify the **owner** and **group** columns
3. Check who owns your files

**Format:** `-rw-r--r-- 1 owner group size date filename`

Document: What's the difference between owner and group?

---

### Task 2: Basic chown Operations (20 minutes)

1. Create file `devops-file.txt`
2. Check current owner: `ls -l devops-file.txt`
![alt text]({A938ADB0-235F-464E-B3F1-BD3ADA3FB860}.png)
3. Change owner to `tokyo` (create user if needed)
![alt text]({E4750DD5-8A53-4CE1-88AA-C8846C94C41E}.png)
4. Change owner to `berlin`
![alt text]({7808EA0D-92E7-4B75-8EEF-CB3909ED2189}.png)
5. Verify the changes

**Try:**
```bash
sudo chown tokyo devops-file.txt
```

---

### Task 3: Basic chgrp Operations (15 minutes)

1. Create file `team-notes.txt`
2. Check current group: `ls -l team-notes.txt`
3. Create group: `sudo groupadd heist-team`
![alt text]({96913952-3F50-4A42-B9F7-30789B339D8C}.png)
4. Change file group to `heist-team`
5. Verify the change
![alt text]({3554BE68-0CD6-4B2B-91F3-EDEC5F21CD24}.png)
---

### Task 4: Combined Owner & Group Change (15 minutes)

Using `chown` you can change both owner and group together:

1. Create file `project-config.yaml`
2. Change owner to `professor` AND group to `heist-team` (one command)
![alt text]({CF9D6622-C92A-4AB9-80AD-B1D3844B7B7A}.png)
3. Create directory `app-logs/`
4. Change its owner to `berlin` and group to `heist-team`
![alt text]({D0110AA6-B5CF-4E58-BEC4-E75A7955DD85}.png)
**Syntax:** `sudo chown owner:group filename`

---

### Task 5: Recursive Ownership (20 minutes)

1. Create directory structure:
   ```
   mkdir -p heist-project/vault
   mkdir -p heist-project/plans
   touch heist-project/vault/gold.txt
   touch heist-project/plans/strategy.conf
   ```
![alt text]({CEB70092-84BC-46A0-B84E-D59A29E42050}.png)


![alt text]({316055C7-34F2-48C9-BF94-4BD33E4B2ECF}.png)
2. Create group `planners`: `sudo groupadd planners`

3. Change ownership of entire `heist-project/` directory:
   - Owner: `professor`
   - Group: `planners`
   - Use recursive flag (`-R`)
   ![alt text]({B367FB5E-3A7D-4C37-A0FC-8DB2E1F386DF}.png)

4. Verify all files and subdirectories changed: `ls -lR heist-project/`
![alt text]({FDF81342-7D57-41CE-83E0-1A8FEB9826C9}.png)
---

### Task 6: Practice Challenge (20 minutes)

1. Create users: `tokyo`, `berlin`, `nairobi` (if not already created)
2. Create groups: `vault-team`, `tech-team`
3. Create directory: `bank-heist/`
4. Create 3 files inside:
   ```
   touch bank-heist/access-codes.txt
   touch bank-heist/blueprints.pdf
   touch bank-heist/escape-plan.txt
   ```

![alt text]({1AFF2CD7-9222-4B3B-9A8C-6B9347F738A8}.png)

![alt text]({E407B468-DE11-4491-96B1-AF1A9CB253EB}.png)

5. Set different ownership:
   - `access-codes.txt` → owner: `tokyo`, group: `vault-team`
   - `blueprints.pdf` → owner: `berlin`, group: `tech-team`
   - `escape-plan.txt` → owner: `nairobi`, group: `vault-team`
![alt text]({AEF329F8-8289-4A0C-B4D6-C3335F5A530C}.png)
**Verify:** `ls -l bank-heist/`


![alt text]({05E4943C-0088-4AF3-A4E8-D3DDC838C452}.png)

sudo chown tokyo:vault-team access-code.txt
sudo chown berlin:tech-team blueprints.pdf
sudo chown nairobi:vault-team escape-plan.txt

---


