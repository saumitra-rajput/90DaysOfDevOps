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
  - journalctl -u docker
  ![alt text](image-5.png)
  - journalctl -u docker -g "error"
  ![alt text](image-4.png)
  - precisically top 10 or -n 2 result using head -n
  ![alt text](image-6.png)
  - bottom 10 or -n 2 result using tail -n 2
  ![alt text](image-7.png)
- Pick **one service on your system** (example: `ssh`, `cron`, `docker`) and inspect it
  - cron
  ![alt text](image-8.png)
  - ssh
  ` sudo journalctl -u ssh -g started | tail`
  ![alt text](image-9.png)
  - `sudo journalctl -u docker -g started | tail -n 2`
  ![alt text](image-10.png)
- Keep it **simple and actionable**

Suggested structure for `linux-practice.md`:
- Process checks
- Service checks
- Log checks
- Mini troubleshooting steps