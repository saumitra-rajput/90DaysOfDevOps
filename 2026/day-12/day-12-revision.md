# Day 12 – Breather & Revision (Days 01–11)

## Goal
Take a **one-day pause** to consolidate everything from Days 01–11 so you don’t forget the fundamentals you just built.


## What to Review (pick at least one per section)
- **Mindset & plan:** revisit your Day 01 learning plan—are your goals still right? any tweaks?  
Yes, I am still stick to my plan somedays i missed pushing my code to gh. but i covered it next day.
- **Processes & services:** rerun 2 commands from Day 04/05 (e.g., `ps`, `systemctl status`, `journalctl -u <service>`); jot what you observed today.  
  - ps shows us active process.
  - systemctl status --all using flag all we can see all system processes.
  - journalctl -u servicename help us to see the journal logs about the service
- **File skills:** practice 3 quick ops from Days 06–11 (e.g., `echo >>`, `chmod`, `chown`, `ls -l`, `cp`, `mkdir`).  
 Done
- **Cheat sheet refresh:** skim your Day 03 commands—highlight 5 you’d reach for first in an incident.  
- **User/group sanity:** recreate one small scenario from Day 09 or Day 11 (create a user or change ownership) and verify with `id`/`ls -l`.

## Mini Self-Check (write short answers in `day-12-revision.md`)
1) Which 3 commands save you the most time right now, and why?  
vim example.sh - I like to automate thing just put in the file and execute it and things will be executed accordingly.
2) How do you check if a service is healthy? List the exact 2–3 commands you’d run first.  
systemctl status servicename
systemctl list-unit-files | grep nginx
journalctl -u nginx or service name
3) How do you safely change ownership and permissions without breaking access? Give one example command.  
4) What will you focus on improving in the next 3 days?

- Leaning Bash scripting.
- practice more commands
- Break and fix things

## Suggested Flow (30–45 minutes)
- 10 min: skim notes from each day, update Day 01 plan if needed.  
- 15–20 min: rerun a tiny hands-on set (process check, service check, file permission change).  
- 5–10 min: write the self-check answers and key takeaways.

## Tips
- Keep it light—this is about retention, not new concepts.  
- If something felt shaky this week (e.g., `chmod` numbers, `journalctl` flags), practice that specifically.  
- Small wins: one screenshot of a command rerun + 5 bullet notes is enough.
