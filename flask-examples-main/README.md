# 🚀 Flask Examples using Docker

A beginner-friendly collection of **Flask applications** designed to help you learn Flask fundamentals while running everything inside Docker.

Each example focuses on a different Flask feature, allowing you to understand concepts step by step instead of building a large application all at once.

---

# 📚 What You Will Learn

* Build Docker images using a Dockerfile
* Run Flask applications inside Docker
* Understand Flask project structure
* Create routes and views
* Render HTML templates
* Handle HTML forms
* Work with databases
* Send emails using Flask
* Implement caching
* Handle HTTP requests and responses
* Manage Python dependencies with `requirements.txt`

---

# 🎯 Project Goal

The goal of this project is to learn Flask through practical examples.

Each folder demonstrates a specific Flask feature so you can understand how individual components work before combining them into larger applications.

---

# 🏗 Project Architecture

```text
              Browser
                 │
         http://localhost:5000
                 │
                 ▼
        Docker Container
                 │
                 ▼
          Flask Application
                 │
        Process Request
                 │
                 ▼
             Response
                 │
                 ▼
              Browser
```

---

# 📁 Project Structure

```text
flask-examples-main/

├── assets/
├── cache/
├── database/
├── email/
├── form/
├── hello/
├── http/
├── template/
├── Dockerfile
├── requirements.txt
├── README.md
├── CHANGES.md
└── LICENSE
```

---

# 📂 Example Description

| Folder        | Description                                            |
| ------------- | ------------------------------------------------------ |
| **hello/**    | Basic Flask application                                |
| **form/**     | Handle user input using HTML forms                     |
| **template/** | Render dynamic HTML using Jinja templates              |
| **database/** | Connect Flask with a database                          |
| **email/**    | Send emails using Flask                                |
| **cache/**    | Improve performance using caching                      |
| **http/**     | Work with HTTP methods and responses                   |
| **assets/**   | Serve static files such as CSS, JavaScript, and images |

---

# ⚙️ Technologies Used

* Python
* Flask
* Docker
* HTML
* Jinja2
* SQLite / Database Examples
* Ubuntu

---

# 🐳 Docker Components Used

## Dockerfile

The Dockerfile creates a Docker image for the Flask application.

It is responsible for:

* Installing Python
* Installing Flask and dependencies
* Copying project files
* Setting the working directory
* Starting the Flask application

---

# 🔄 Request Flow

```text
Browser
    │
    ▼
localhost:5000
    │
    ▼
Docker Container
    │
    ▼
Flask Application
    │
    ▼
Python Processes Request
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
cd Docker-Learning/flask-examples-main
```

### 3. Build the Docker image

```bash
docker build -t flask-examples .
```

### 4. Run the container

```bash
docker run -d \
  --name flask-examples \
  -p 5000:5000 \
  flask-examples
```

### 5. Open your browser

```text
http://localhost:5000
```

---

# ⭐ Conclusion

This repository provides a hands-on introduction to Flask using Docker through a collection of focused examples.

By exploring each example, you'll learn how Flask applications are structured, how requests are processed, how templates and forms work, how databases and caching are integrated, and how Docker simplifies application deployment. These concepts provide a strong foundation for building and deploying Python web applications.
