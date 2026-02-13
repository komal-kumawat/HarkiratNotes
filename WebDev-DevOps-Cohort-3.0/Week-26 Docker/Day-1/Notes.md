
![slides](https://projects.100xdevs.com/tracks/docker-2/docker-2-1)
# DOCKER
- Docker is a containerization platform that packages applications and their dependencies to run reliably across different environments.
- slides: https://projects.100xdevs.com/tracks/docker-2/docker-2-13
## DOCKER CONTAINER
- A Docker container is a lightweight, isolated environment that runs an application along with all its dependencies using a Docker image.

- A Docker container is a standardized, executable unit that contains application code, libraries, and dependencies to run consistently across different systems.


**Docker in simple words:**

Docker is a tool that **packs your app and everything it needs into one box** so it runs the **same everywhere**.

### Easy example

Imagine your app is a **tiffin** 🍱

* Food = your code
* Containers = the box that keeps everything together

No matter where you take it, the food stays the same.

### What Docker does

* Puts your app + libraries + settings together
* Runs it in a small, isolated space called a **container**
* Works on your laptop, server, or cloud without changes

### Why people use Docker

* No “it works on my system” problems ❌
* Very fast to start
* Uses less memory than virtual machines
* Makes deployment easy

### One-line definition

> **Docker helps you build, ship, and run applications consistently anywhere.**


## Why containers
- Everyone has different Operating systems
- Steps to run a project can vary based on OS
- Extremely harder to keep track of dependencies as project grows


## Benefits of using docker
- Let you describe your configuration in a single file
- Can run in isolated environments
- Makes Local setup of OS projects a breeze
- Makes installing auxiliary services/DBs easy


## Steps of installing docker

## ✅ Installing Docker on **macOS** (your case)

### 1. Download Docker Desktop

* Go to **docker.com**
* Click **Download Docker Desktop for Mac**
* Choose:

  * **Apple Silicon** (M1/M2/M3) ✅
  * **Intel** (older Macs)

---

### 2. Install Docker

* Open the downloaded **.dmg** file
* Drag **Docker** into the **Applications** folder

---

### 3. Start Docker

* Open **Docker Desktop** from Applications
* Allow required permissions
* Wait until Docker shows **“Docker is running”**

---

### 4. Verify Installation

Open **Terminal** and run:

```bash
docker --version
```

If it shows a version → ✅ Docker installed successfully

---

## 🔁 Steps for **Windows**

1. Download **Docker Desktop for Windows**
2. Enable **WSL 2** (Docker will guide you)
3. Install and restart
4. Run `docker --version`

---

## 🔁 Steps for **Linux (Ubuntu)**

```bash
sudo apt update
sudo apt install docker.io
sudo systemctl start docker
docker --version
```

---

## 🎯 summarising docker installation steps

> Download Docker Desktop → Install → Start Docker → Check version

### Components of docker


## Why these terms matter

As a **full-stack developer**, Docker helps you **run apps, databases, and services easily** without worrying about setup on different machines.

---

## 1️⃣ Docker Engine

**Docker Engine** is the **core software** that actually runs Docker.

### What it does

* Builds Docker images
* Creates and runs containers
* Manages container lifecycle (start, stop, delete)

### In simple words----

> **Docker Engine is the brain of Docker that runs containers.**

### Important idea

A **container** includes:

* Your application code
* Required OS libraries
* Dependencies

So your app runs **the same everywhere**.

---

## 2️⃣ Docker CLI (Command Line Interface)

**Docker CLI** is how you **give commands to Docker Engine**.

### What it does

* Start containers
* Stop containers
* List running containers
* Pull images from registry

### Example command

```bash
docker run -d -p 27017:27017 mongo
```

### What this means

* `docker run` → create & start a container
* `-d` → run in background (detached mode)
* `-p 27017:27017` → map local port to container port
* `mongo` → use MongoDB image from registry

📌 Result: **MongoDB runs without installing it locally**

---

### 💡 Important note

Docker CLI is **not the only way** to talk to Docker Engine.

* Docker Engine also exposes a **REST API**
* Tools like Docker Desktop, Kubernetes, CI/CD pipelines use this API

> CLI → REST API → Docker Engine

---

## 3️⃣ Docker Registry

A **Docker Registry** is a place where **Docker images are stored and shared**.

### Think of it like

> **GitHub for Docker images**

* GitHub → stores source code
* Docker Registry → stores built images

### Why it exists

* Share images
* Reuse images
* Deploy apps easily

### Docker Hub

* Official registry: **dockerhub.com**
* Public images available for free

### Example

* MongoDB image:
  👉 `https://hub.docker.com/_/mongo`

When you run:

```bash
docker run mongo
```

Docker automatically:

1. Checks locally
2. If not found → downloads from Docker Hub
3. Runs it as a container

---

## 🧠 Quick summary (interview-ready)

* **Docker Engine** → runs containers
* **Docker CLI** → tool to control Docker Engine
* **Docker Registry** → stores & shares Docker images



## Image v/s Container


| Docker Image                                 | Docker Container                      |
| -------------------------------------------- | ------------------------------------- |
| A **blueprint / template** of an application | A **running instance** of an image    |
| Static (does not run)                        | Dynamic (currently running)           |
| Contains code, runtime, libraries, configs   | Uses image content to execute the app |
| Read-only                                    | Read + write                          |
| Stored in Docker Registry (Docker Hub)       | Runs on Docker Engine                 |
| Can exist without being executed             | Cannot exist without an image         |
| Similar to **codebase on GitHub**            | Similar to running `node index.js`    |
| One image can create many containers         | Each container is isolated            |

### One-line summary

- **Docker Image = source code**  
- **Docker Container = running application**



## Docker commands:-

## 🔹 Basic Docker Commands

```bash
docker --version        # Check Docker version
docker info             # Docker system info
docker help             # List all commands
docker ps
```

---

## 🔹 Image Commands

```bash
docker images           # List all images
docker pull mongo       # Download image from Docker Hub
docker rmi <image_id>   # Delete an image
```

---

## 🔹 Container Commands

```bash
docker run <image>                      # Create & run container
docker run -d -p 3000:3000 <image>      # Run in background with port
docker ps                               # Running containers
docker ps -a                            # All containers
docker stop <container_id>              # Stop container
docker start <container_id>             # Start container
docker restart <container_id>           # Restart container
docker rm <container_id>   
             # Delete container
docker kill <container_id>  # Immediately stop a running container
```

---

## 🔹 Exec & Logs

```bash
docker exec -it <container_id> bash     # Enter running container
docker logs <container_id>              # View container logs
```

---

## 🔹 Build & Push Images

```bash
docker build -t myapp .                 # Build image
docker tag myapp username/myapp         # Tag image
docker push username/myapp              # Push to Docker Hub
```

---

## 🔹 Network & Volume

```bash
docker network ls
docker volume ls
```

---

## 🔹 System Cleanup

```bash
docker system df        # Disk usage
docker system prune     # Remove unused data
```

---

## 🧠 Most-used commands (remember these!)

```bash
docker run
docker ps
docker kill <container_id>
docker build
docker stop
docker rm
docker images
docker exec
```

---

## 🎯 One-line summary

> **Docker commands help you run, manage, and delete containers and images from the terminal.**


## Docker file 
### 📄 Dockerfile — explained simply

A **Dockerfile** is a **text file** that tells Docker **how to build an image** for your application.

---

## 🧠 In simple words

> **Dockerfile = recipe**
> Docker follows this recipe step-by-step to create a Docker image.

---

## 🧱 What a Dockerfile contains

It describes:

* Base OS or runtime
* App code
* Dependencies
* Commands to run the app

---

## 📌 Example Dockerfile (Node.js)

```dockerfile
FROM node:18
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 3000
CMD ["node", "index.js"]
```

---

## 🔍 Line-by-line explanation

| Line              | Meaning                              |
| ----------------- | ------------------------------------ |
| `FROM node:18`    | Base image (Node installed)          |
| `WORKDIR /app`    | Working directory inside container   |
| `COPY`            | Copy files into image                |
| `RUN npm install` | Install dependencies                 |
| `EXPOSE 3000`     | Inform container port                |
| `CMD`             | Command to run when container starts |

---

## 🔄 How Dockerfile is used

```bash
docker build -t myapp .
docker run -p 3000:3000 myapp
```

---

## 🧠 Mental model

> **Dockerfile → Image → Container**

---

## 📋 Common Dockerfile instructions

| Instruction | Purpose                        |
| ----------- | ------------------------------ |
| FROM        | Base image                     |
| WORKDIR     | Set directory                  |
| COPY / ADD  | Copy files                     |
| RUN         | Execute command while building |
| CMD         | Run app when container starts  |
| ENTRYPOINT  | Main executable                |
| EXPOSE      | Declare port                   |

---

## 🎯 One-line definition

> **A Dockerfile is a set of instructions used to build a Docker image.**


