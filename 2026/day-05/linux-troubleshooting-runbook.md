# Day 05 – Linux Troubleshooting Drill: CPU, Memory, and Logs

## Task

## Guidelines
Follow these rules while creating your runbook:

- Run and record output for **at least 8 commands** (save snippets in your runbook)  
  - **Environment basics (2):** `uname -a`, `lsb_release -a` (or `cat /etc/os-release`)  
    - uname -a
    ![alt text](image.png)
    - cat /etc/os-release
    ![alt text](image-1.png)
  - **Filesystem sanity (2):** create a throwaway folder and file, e.g., `mkdir /tmp/runbook-demo`, `cp /etc/hosts /tmp/runbook-demo/hosts-copy && ls -l /tmp/runbook-demo`  
    - ![alt text](image-3.png)
    - ![alt text](image-2.png)

  - **CPU / Memory (2):** `top`/`htop`/`ps -o pid,pcpu,pmem,comm -p <pid>`, `free -h`, `vm_stat` (mac)  
    - top
    ![alt text](image-4.png)
    - htop
    ![alt text](image-5.png)
    - ps -o pid,pcpu,pmem,comm -p PID
    ![alt text](image-7.png)
    - free-h
    ![alt text](image-8.png)
    - vmstat
    ![alt text](image-6.png)
  - **Disk / IO (2):** `df -h`, `du -sh /var/log`, `iostat`/`vmstat`/`dstat`  
    - df -h
    ![alt text](image-9.png)
    - du -sh /var/log
    ![alt text](image-10.png)
    - iostat
    ![alt text](image-11.png)
    - vmstat
    ![alt text](image-12.png)
    - dstat
    ![alt text](image-13.png)

  - **Network (2):** `ss -tulpn`/`netstat -tulpn`, `curl -I <service-endpoint>`/`ping`  
    - ss -tulpn
    ![alt text](image-15.png)
    - netstat -tulpn
    ![alt text](image-14.png)
    - curl -I google.com
    ![alt text](image-16.png)

  - **Logs (2):** `journalctl -u <service> -n 50`, `tail -n 50 /var/log/<file>.log`

    - tail -n 50 /var/log/logfilename
    - journalctl -u <service> -n 50