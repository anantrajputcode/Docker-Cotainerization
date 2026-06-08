# WebSchool — Dockerized School Website

A static school website served with **Nginx**, containerized with **Docker** and published to Docker Hub.

---

## Docker Hub

**Image:** `anantrajputcode/webschool:1.0.0`

```bash
docker pull anantrajputcode/webschool:1.0.0
```

---

## Getting Started

### Prerequisites

- [Docker](https://docs.docker.com/get-docker/) installed on your machine

### Run the Container

```bash
docker run -d -p 8080:80 anantrajputcode/webschool:1.0.0
```

Then open your browser and visit: [http://localhost:8080](http://localhost:8080)

---

## Project Structure

```
Docker-Capstone-Project1/
└── school-website/       # Static HTML/CSS/JS files served by Nginx
Dockerfile                # Docker build instructions
```

---

## Dockerfile

```dockerfile
FROM nginx:latest
COPY ./Docker-Capstone-Project1/school-website /usr/share/nginx/html
EXPOSE 80
```

| Instruction | Description |
|-------------|-------------|
| `FROM nginx:latest` | Uses the official Nginx base image |
| `COPY` | Copies the static website files into Nginx's web root |
| `EXPOSE 80` | Exposes port 80 for HTTP traffic |

---

## Build & Push (for maintainers)

### Build the Image

```bash
docker build -t anantrajputcode/webschool:1.0.0 .
```

### Run Locally

```bash
docker run -d -p 8080:80 anantrajputcode/webschool:1.0.0
```

### Push to Docker Hub

```bash
docker login
docker push anantrajputcode/webschool:1.0.0
```

---

## Stop the Container

```bash
# Find the container ID
docker ps

# Stop it
docker stop <container_id>
```

---

## Tech Stack

- **Nginx** — Web server
- **Docker** — Containerization
- **HTML/CSS/JS** — Static school website

---

## Author

**Anant Rajput**
- Docker Hub: [anantrajputcode](https://hub.docker.com/u/anantrajputcode)

---

## License

This project is open source and available under the [MIT License](LICENSE).