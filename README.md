# 📝 Todo App — Containerized with Docker

A simple Node.js todo app containerized using Docker. This project demonstrates my ability to write Dockerfiles, build images, and run containers — core skills for a DevOps or backend role.

---

## 🛠️ Tech Stack

- **Runtime:** Node.js 20
- **Base Image:** node:20-alpine
- **Containerization:** Docker

---

## 🐳 Running with Docker

**Step 1 — Clone the repo:**
```bash
https://github.com/rhythmD-ops/Docker_todo_simple

cd 
**Step 2 — Build the image:**
```bash
docker build -t todo-app .
```

**Step 3 — Run the container:**
```bash
docker run -p 3000:3000 todo-app
```

**Step 4 — Open in browser:**
```
http://localhost:3000
```

---

## 📁 Project Structure

```
├── src/
│   └── index.js       # Main application file
├── package.json       # Dependencies and scripts
├── Dockerfile         # Docker image instructions
├── .dockerignore      # Files excluded from Docker build
└── README.md
```

---

## 🔍 What the Dockerfile Does

| Instruction | What it does |
|---|---|
| `FROM node:20-alpine` | Uses a lightweight Node.js base image |
| `WORKDIR /app` | Sets the working directory inside the container |
| `COPY package.json .` | Copies dependency list before installing |
| `RUN npm install` | Installs app dependencies |
| `COPY . .` | Copies source code into the container |
| `EXPOSE 3000` | Documents the port the app runs on |
| `CMD node src/index.js` | Starts the app when container runs |

---

## 💡 Key Concepts Applied

- **Layer caching** — `package.json` is copied and dependencies installed before source code is copied, so Docker only re-runs `npm install` when dependencies actually change — not on every code change.
- **Alpine base image** — Using `node:20-alpine` instead of `node:20` keeps the image significantly smaller.
- **`.dockerignore`** — Excludes `node_modules` from being copied in, since they are installed fresh inside the container.

---

## 📚 Learning Resource

This project was built while learning Docker from the ground up. More containerized projects coming soon including multistage builds and Docker Compose.
