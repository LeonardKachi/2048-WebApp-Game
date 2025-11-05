# 2048 WebApp Game (Containerized)

A containerized version of the classic **2048** browser game, built and deployed using **Docker** and **Nginx**.  
This project demonstrates modern DevOps practices packaging a static web application into a reproducible, portable container.

---

## Project Overview

**Goal:** Host and serve the 2048 game in a Docker container, accessible through a web browser.  
**Focus:** Lightweight containerization, efficient Dockerfile structure, and deployment consistency.

---

## Motivation

This project was created to:
- Practice Docker fundamentals in a real-world scenario.
- Understand how Nginx serves static content inside containers.
- Troubleshoot and fix path and command issues during container build and run.
- Build a small but complete DevOps pipeline (code → container → deployment).

---

## Tech Stack

- **Language / Framework:** HTML, CSS, JavaScript  
- **Web Server:** Nginx  
- **Containerization:** Docker  
- **Environment:** Ubuntu (via WSL)

---

## How to Run Locally

1. **Clone the Repository**
   ```bash
   git clone https://github.com/LeonardKachi/2048-WebApp-Game.git
   cd 2048-WebApp-Game
   ````

2. **Build the Docker Image**

   ```bash
   docker build -t 2048-game .
   ```

3. **Run the Container**

   ```bash
   docker run -d -p 8081:80 2048-game
   ```

4. **Play the Game**
   Open your browser and navigate to:

   ```
   http://localhost:8081
   ```

---

## Project Structure

```
2048-WebApp-Game/
│
├── game/                  # Static web files (HTML, CSS, JS)
├── Dockerfile             # Container build configuration
└── README.md              # Project documentation
```

---

## Dockerfile Summary

The Dockerfile uses the official **Nginx base image**, copies the game files into the container, and exposes port `80`.

Example:

```dockerfile
FROM nginx:alpine

COPY ./game /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
```

---

## Lessons Learned

* Debugging container build errors and path issues.
* Correctly mapping ports for static web apps.
* Understanding how Nginx serves content in minimal environments.
* Importance of proper file structuring inside Docker images.

---

## Next Steps

* Push image to Docker Hub or AWS ECR.
* Deploy on AWS ECS, Kubernetes, or Azure Container Apps.
* Add CI/CD pipeline for automated builds.
* Add analytics or logging to monitor user interactions.

---

## Repository

[https://github.com/LeonardKachi/2048-WebApp-Game](https://github.com/LeonardKachi/2048-WebApp-Game)

---

## Author

**Leonard Kachi Henry**
Cloud Security Engineer | DevSecOps | 
[Portfolio](https://leonardkachi.github.io/Portfolio-website)

---
