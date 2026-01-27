## Task 2
Today’s goal is to **understand how Linux works under the hood**.

You will create a short note that explains:
- The core components of Linux (kernel, user space, init/systemd)
  - Kernel:The kernel is the core of the operating system, acting as a bridge between software applications and the hardware
  - User Space:User space is where user applications, system libraries, and most system utilities run.
  - init/systemd: <init> system is the very first user-space process started by the kernel, assigned Process ID (PID) 1. Its primary role is to initialize the rest of the user space and manage system services and processes throughout the system's runtime until shutdown. 

- How processes are created and managed
  - Everthing in the Linux is process.
  - Each Proccess has a unique process ID.
  - we can use `ps` command to check all the processes by adding flag accordingly.
    - `ps aux`: It shows all processes, in user format, including those without a terminal
    - `-A or -e`: Select all processes.
    - `-x or x`: Shows process like ( deamons and background services)
    - `-u or u`: Display in user oriented format
    
- What systemd does and why it matters

  Systemd is the default, modern init system and service manager for most Linux distributions, functioning as PID 1 to boot the system and manage processes, services, and hardware. It organizes tasks into units (services, mount points) to enable parallel booting
  This is the foundation for all troubleshooting you will do as a DevOps engineer.
    What Systemd Does:
    - Initializes the System: As the first process (PID 1), it starts all other user-space processes.
    - Manages Services: It handles starting, stopping, restarting, and monitoring services (daemons) using systemctl.
    - Parallelization: It speeds up boot times by launching services in parallel rather than sequentially.
    - Dependency Management: It defines relationships between services (e.g., "Service A must start before Service B").
    - Journaling/Logging: It provides a centralized, binary logging system (journald) for system messages.

## Guidelines
Follow these rules while creating your notes:

- Explain **process states** (running, sleeping, zombie, etc.)
  - running: The process is actively executing instructions on the CPU.
  - sleeping:A sleeping process is waiting for a specific event or resource example: waiting for input.
  - zombie:A zombie process is a process that has finished execution but still has an entry in the process table.
  - stopped:The process has been suspended, usually by receiving a signal like SIGSTOP or SIGTSTP
  - Runnable: The process has everything it needs to run, but the CPU is busy with another task. It is waiting in a queue to be scheduled.

- List **5 commands** you would use daily
  - cd: change the directory.
  - man: for reading command manual.
  - grep: used to search for specific text patterns within files 
  - ls -la: list the all files.
  - df -h: Displays disk space in a human-readable format.
- Keep it **short and practical** (under 1 page)
- Use bullet points and short headings
