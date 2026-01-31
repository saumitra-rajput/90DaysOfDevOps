# Day 04 – Linux Practice: Processes and Services

## Task
---



## Guidelines
Follow these rules while creating your practice note:

- Run and record output for **at least 6 commands**
- Include **2 process commands** (`ps`, `top`, `pgrep`, etc.)
- Include **2 service commands** (`systemctl status`, `systemctl list-units`, etc.)
  - systemctl status docker
  ![alt text](image.png)
  - systemctl list-unit-files
  ![alt text](image-1.png)
  - systemctl list-units
  ![alt text](image-2.png)
  - systemctl list-units and systemctl list-unit-files | grep docker
  ![alt text](image-3.png)

- Include **2 log commands** (`journalctl -u <service>`, `tail -n 50`, etc.)

- Pick **one service on your system** (example: `ssh`, `cron`, `docker`) and inspect it
- Keep it **simple and actionable**

Suggested structure for `linux-practice.md`:
- Process checks
- Service checks
- Log checks
- Mini troubleshooting steps