# Day 37 – Docker Revision & Cheat Sheet

## Goal
Take a **one-day pause** to consolidate everything from Days 29–36 so Docker actually sticks.

## Expected Output
- A markdown file: `docker-cheatsheet.md`
- A markdown file: `day-37-revision.md` with self-check answers

---

## Self-Assessment Checklist
Mark yourself honestly — **can do**, **shaky**, or **haven't done**:

- [0] Run a container from Docker Hub (interactive + detached)
- [0] List, stop, remove containers and images
- [0] Explain image layers and how caching works
- [0] Write a Dockerfile from scratch with FROM, RUN, COPY, WORKDIR, CMD
- [0] Explain CMD vs ENTRYPOINT
- [0] Build and tag a custom image
- [0] Create and use named volumes
- [0] Use bind mounts
- [0] Create custom networks and connect containers
- [0] Write a docker-compose.yml for a multi-container app
- [0] Use environment variables and .env files in Compose
- [0] Write a multi-stage Dockerfile
- [0] Push an image to Docker Hub
- [0] Use healthchecks and depends_on

---

## Quick-Fire Questions
Answer from memory, then verify:
1. What is the difference between an image and a container?
- Image: image is script of files or command having os to runtime info that will work on container
- container: a block where image will run
2. What happens to data inside a container when you remove it?
- lifecycle of container is like born when you run it, can be stop but when you remove it data is lost along with the container unless you create and mount the volume.
3. How do two containers on the same custom network communicate?
- they communicate via concepts called bridge we have 7 different types of networks, each container by default will have bridge network which is in standby ready to connnect or can be connect to other containers
4. What does `docker compose down -v` do differently from `docker compose down`?
- docker compose down simple bring down what you build via compose file (it do not delete created volumes)
- docker compose down -v bring down what you build via compose and also remove built networks

5. Why are multi-stage builds useful?
- helpful when you wants to use the output of stage in other stages.
- reduce the size

6. What is the difference between `COPY` and `ADD`?
- COPY: This simply copies app.py from your local directory to /app inside the image.
- ADD: If the file is compressed (.tar.gz), ADD will automatically extract it.
7. What does `-p 8080:80` mean?
- local host port 8080 is mapped to container port 80
8. How do you check how much disk space Docker is using?
docker system df
---

## Build Your Docker Cheat Sheet
Create `docker-cheatsheet.md` organized by category:
- **Container commands** — run, ps, stop, rm, exec, logs
- **Image commands** — build, pull, push, tag, ls, rm
- **Volume commands** — create, ls, inspect, rm
- **Network commands** — create, ls, inspect, connect
- **Compose commands** — up, down, ps, logs, build
- **Cleanup commands** — prune, system df
- **Dockerfile instructions** — FROM, RUN, COPY, WORKDIR, EXPOSE, CMD, ENTRYPOINT



Keep it short — one line per command, something you'd actually reference on the job.

---

## Revisit Weak Spots
Pick **2 topics** you marked as shaky and redo the hands-on tasks from that day.

---

## Suggested Flow (45–60 minutes)
- 10 min: go through the checklist honestly
- 10 min: answer quick-fire questions
- 20 min: build your cheat sheet
- 10 min: redo one weak area

---

## Submission
1. Add `docker-cheatsheet.md` and `day-37-revision.md` to `2026/day-37/`
2. Commit and push to your fork

---

## Learn in Public
Share your Docker cheat sheet on LinkedIn — help others revise too.

`#90DaysOfDevOps` `#DevOpsKaJosh` `#TrainWithShubham`

Happy Learning!
**TrainWithShubham**
