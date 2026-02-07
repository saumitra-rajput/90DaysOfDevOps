# Day 13 – Linux Volume Management (LVM)

## Task



---

## Challenge Tasks

### Task 1: Check Current Storage
Run: 
`lsblk`
![alt text](image.png)
`pvs`

`vgs`

`lvs`
![alt text](image-1.png)

`df -h`
![alt text](image-2.png)


### Created elastic volume in aws
![alt text](image-3.png)


### Attached the volume to linux machine
![alt text](image-4.png)

### Task 2: Create Physical Volume
```bash
pvcreate /dev/sdb   # or your loop device
pvs
```
![alt text](image-5.png)


### Task 3: Create Volume Group
```bash
vgcreate devops-vg /dev/sdb
vgs
```
![alt text](image-6.png)

### Task 4: Create Logical Volume
```bash
lvcreate -L 500M -n app-data devops-vg
lvs
```
![alt text](image-7.png)

### Task 5: Format and Mount
Before mount df -h 
![alt text](image-10.png)

mkfs.ext4 /dev/devops-vg/app-data
![alt text](image-12.png)
mkdir -p /mnt/app-data

![alt text](image-11.png)
mount /dev/devops-vg/app-data /mnt/app-data
df -h /mnt/app-data
![alt text](image-13.png)


### Task 6: Extend the Volume
```bash
lvextend -L +200M /dev/devops-vg/app-data
resize2fs /dev/devops-vg/app-data
df -h /mnt/app-data
```

### Task 6: Extend the Volume
![alt text](image-9.png)


After extending
![alt text](image-8.png)

### Direct mount
before mount
![alt text](image-14.png)

making dir and formatting disk
![alt text](image-15.png)

Disk mounted and showing status
![alt text](image-16.png)
---


### sudo umount /mnt/mountname

![alt text](image-17.png)

## Documentation

Create `day-13-lvm.md` with:
- Commands used
- Screenshots of outputs
- What you learned (3 points)

---

## Submission
1. Add your `day-13-lvm.md` to `2026/day-13/`
2. Commit and push

---
