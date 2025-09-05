# Docker & Docker Compose Training

This repository contains exercises for practicing **Docker** and **Docker Compose**.  
The goal is to understand containerization, volumes, networks, secrets, environment variables, and multi-service orchestration.

---

## 🗂 Repository Structure

├─ 1
│ ├─ compose.yaml
│ ├─ msg.txt
│ └─ image/
│ └─ Dockerfile
├─ 2
│ ├─ compose.yaml
│ └─ image/
│ ├─ Dockerfile
│ ├─ src/index.js
│ └─ package.json
├─ 3
│ ├─ compose.yaml
│ ├─ db_password.txt
│ └─ .env
└─ 4
├─ compose.yaml
├─ db_password.txt
├─ .env
└─ debian_psql/
└─ Dockerfile


---

## 📌 Exercises Overview

### Exercise 1 – Hello Message
- Create a Debian-based container that displays a message from `/opt/msg.txt`.
- Uses **bind mount** to allow changing the message without rebuilding the image.
- Command: `/bin/cat /opt/msg.txt`

### Exercise 2 – Node.js Server
- Simple Node.js HTTP server listening on port 3030.
- Dockerfile installs dependencies and starts the server.
- Compose exposes port `3030` to localhost.

### Exercise 3 – Postgres & Volumes
- Start a PostgreSQL container with environment variables and secrets.
- Demonstrates **volume usage** for persisting database data.
- `.env` and `db_password.txt` are used for configuration.

### Exercise 4 – Postgres Client & Network
- Build a Debian-based container with `psql` installed.
- Connects to the PostgreSQL container via Docker network.
- Uses `healthcheck` to wait for the DB to be ready.
- Demonstrates **environment variables** for DB credentials.

### Exercise 5 – Full Compose Integration
- Combines Exercises 1–4 in a single `docker-compose.yml`.
- All services can be launched simultaneously with `docker compose up --build`.
- Demonstrates multi-service orchestration, networks, volumes, secrets, and environment variables.

---

## ⚡ How to Run

```bash
# Go to the folder of the exercise
cd 1
docker compose up --build

# Repeat for exercises 2–4

```

---

📝 Notes

All ports are exposed only to localhost.

Secrets and environment variables are used to secure credentials.

Volumes are used to persist data and allow message/file modification without rebuilding images.