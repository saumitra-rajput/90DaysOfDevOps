## Task 3
---

Today’s goal is to **build your Linux command confidence**.

You will create a cheat sheet of commands focused on:
- Process management
  - `ps aux`: To view all the process ID
  - `ps aux | grep "text" <file>`: To view the process with the specific term or details.(grep "Error" server.log)
  - `ps a`: shows the active process
  - `ps x`: shows process for the terminal
  - `ps -e`:
  - `ps -f`: shows UID, PID, PPID, start time, etc
  - `ps -C nginx`:Filter by process name
  - `ps -p 1234`: Filter by process ID
  - `top`: real time linux process
  - `tail`: output or print the last 10 process
  - `uptime`: Show system uptime.
  - `kill`: to kill the process with PID



- File system
  - `ls`: list the files
  - `ls -la`: list all dir/files in readable format
  - `df -h`: display info about storable in human readable format
  - `chgrp`:To change the group of file.
  - `chown`: change owner.
  - `chmod`:change file permisson :chmod 775 test.txt
  - `umask`:User File Creation Mode Mask Default value = 0002 
  - `rm`: remove file with flag -r, -f
  - `find / -name "*.terraform"`: find / -name "*.log"
   
- Networking troubleshooting
  - `hostname -i`: show ip
  - `hostname -I`: shows all ip
  - `netstat`:Displays network connections, routing tables, and listening ports.
  - `ifconfig`: Shows or configures network interfaces.
  - `traceroute`:track the route packets taken from an IP network on their way to the given host.
  - `ping`: to check the connectivity.
  - `curl` : Curl is a tool used to send and receieve date via URL
  - `ip addr show`: shows NICs and need check sensai ifconfig
  - `dig google.com` :interrogating dns name server
  - `wget`: Focuses on downloading files.
  




`ip addr show`: shows NICs and need check sensai ifconfig