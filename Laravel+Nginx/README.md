# 🚀 Laravel + Nginx using Docker

A beginner-friendly project that demonstrates how to run a **Laravel application** inside Docker using **Nginx** as the web server.

The purpose of this project is to understand how Docker containers work together in a real-world Laravel environment while learning the role of each component.

---

# 📚 What You Will Learn

* Build Docker images using a Dockerfile
* Run multiple containers using Docker Compose
* Configure Nginx as a web server
* Connect Nginx with Laravel (PHP-FPM)
* Understand Docker networking
* Learn port mapping
* Organize a production-style project structure

---

# 🎯 Project Goal

Instead of installing PHP, Composer, and Nginx directly on your system, this project runs everything inside Docker containers.

By building this project from scratch, you'll understand how different services communicate and how a Laravel application is served through Nginx.

---

# 🏗 Project Architecture

```text
                Browser
                   │
           http://localhost
                   │
              Port 80
                   │
          ┌─────────────────┐
          │      Nginx      │
          │   Web Server    │
          └─────────────────┘
                   │
          Forwards Request
                   │
          ┌─────────────────┐
          │     Laravel     │
          │     PHP-FPM     │
          └─────────────────┘
                   │
            Process Request
                   │
               Response
                   │
               Browser
```

---

# 📁 Project Structure

```text
Laravel+Nginx/

├── Dockerfile
├── docker-compose.yml
├── nginx/
│   ├── Dockerfile
│   └── nginx.conf
├── app/
├── bootstrap/
├── config/
├── public/
├── resources/
├── routes/
└── ...
```

---

# ⚙️ Technologies Used

* Docker
* Docker Compose
* Laravel
* PHP
* Nginx
* Ubuntu

---

# 🐳 Docker Components Used

## Dockerfile

The Dockerfile creates the Laravel image.

It is responsible for:

* Installing PHP
* Installing required PHP extensions
* Copying the Laravel project
* Setting the working directory
* Starting the PHP-FPM service

---

## docker-compose.yml

Docker Compose manages all containers.

It is responsible for:

* Building Docker images
* Creating a Docker network
* Starting containers
* Connecting services together

---

## Nginx

Nginx works as the web server.

It is responsible for:

* Receiving browser requests
* Serving static files
* Forwarding PHP requests to Laravel (PHP-FPM)

---

# 🔄 Request Flow

```text
Browser
   │
   ▼
localhost:80
   │
   ▼
Nginx
   │
   ▼
Laravel (PHP-FPM)
   │
   ▼
Process Request
   │
   ▼
Response
   │
   ▼
Browser
```

---

# 🚀 How to Run

### 1. Clone the repository

```bash
git clone https://github.com/Arzu-shaikh/Docker-Learning.git
```

### 2. Move into the project

```bash
cd Docker-Learning/Laravel+Nginx
```

### 3. Build the Docker images

```bash
docker compose build
```

### 4. Start the containers

```bash
docker compose up
```

Run in detached mode:

```bash
docker compose up -d
```

### 5. Open your browser

```
http://localhost
```

---

# ⭐ Conclusion

This project demonstrates how to deploy a Laravel application using Docker and Nginx in a clean, production-style environment.

By completing this project, you'll gain practical experience with Docker images, containers, Docker Compose, Nginx configuration, and service communication. These are fundamental skills for PHP development, DevOps, and modern application deployment.
