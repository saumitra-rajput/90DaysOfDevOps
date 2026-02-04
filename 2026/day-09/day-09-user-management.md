# Day 09 – Linux User & Group Management Challenge

## Task
---
Figure out how to:
- Create users and set passwords
- Create groups and assign users
- Set up shared directories with group permissions

---

## Challenge Tasks

### Task 1: Create Users (20 minutes)
![alt text]({4A270CED-D865-40CC-BE57-F36BCC506609}.png)

Create three users with home directories and passwords:
- `tokyo`
![alt text]({1E3A7943-7E26-49F0-9AA6-88009E6A4DA4}.png)

- `berlin` Done
- `professor` Done

![alt text]({16536F08-EB7A-4753-B36E-BD6CAC69B850}.png)
**Verify:** Check `/etc/passwd` and `/home/` directory

---

### Task 2: Create Groups (10 minutes)

Create two groups:
- `developers`
- `admins`

![alt text]({72F9E3A6-1546-4EF0-9A03-86FD50D4954F}.png)
**Verify:** Check `/etc/group`

---

### Task 3: Assign to Groups (15 minutes)

Assign users:
- `tokyo` → `developers`
- `berlin` → `developers` + `admins` (both groups)
![alt text]({6E793928-4F6D-4426-9C54-8FC6C0C50035}.png)

![alt text]({C9BD468B-5A41-407A-89AB-68E25ABBBC76}.png)
- `professor` → `admins`
![alt text]({090E66EE-230B-4070-B78D-0D75F4F236B1}.png)

**Verify:** Use appropriate command to check group membership
![alt text]({84440E47-AB51-47B8-A760-2BFCC1D94908}.png)
---

### Task 4: Shared Directory (20 minutes)

1. Create directory: `/opt/dev-project`
![alt text]({8738B326-9460-436D-8C4C-772A714E6B18}.png)
2. Set group owner to `developers`
![alt text]({E0270187-0623-44CF-996D-70D9268B53CE}.png)
3. Set permissions to `775` (rwxrwxr-x)
![alt text]({C697990E-B733-46AF-811D-5CCDF97E632B}.png)
4. Test by creating files as `tokyo` and `berlin`

![alt text]({B03F590F-5733-480B-92B5-E9CCEAAD3D89}.png)

**Verify:** Check permissions and test file creation
![alt text](image.png)
---

### Task 5: Team Workspace (20 minutes)

1. Create user `nairobi` with home directory
2. Create group `project-team`
3. Add `nairobi` and `tokyo` to `project-team`
4. Create `/opt/team-workspace` directory
![alt text]({3BF36AC3-06FA-4B67-AFFF-642034C5857F}.png)
5. Set group to `project-team`, permissions to `775`
![alt text]({DA406C2E-E8C9-4F75-B4CF-2A9F036C0D2D}.png)

![alt text]({2E0A07FF-B055-4100-AE3C-68FEBD36374B}.png)
6. Test by creating file as `nairobi`
![alt text]({18EB59C8-1D06-42DB-A077-7399C5019329}.png)
---