# MySQL & phpMyAdmin using Docker Compose

This project demonstrates how to run **MySQL 8.0** and **phpMyAdmin** using **Docker Compose**.

## Features

* MySQL 8.0 Database
* phpMyAdmin Web Interface
* Docker Compose
* Persistent Data using Docker Volumes
* Automatic Docker Network
* Easy Deployment

---

## Project Structure

```text
mysql-phpmyadmin/
├── mysql-phpmyadmin-compose.yml
└── README.md
```

---

## Services

### MySQL

* Image: `mysql:8.0`
* Port: `3306`
* Creates:

  * Root User
  * Database
  * Application User
* Stores data in a Docker Volume (`db_data`)

### phpMyAdmin

* Image: `phpmyadmin/phpmyadmin`
* Port: `8080`
* Connects to MySQL using the Docker service name (`db`)

---

## Architecture

```text
Browser
    │
localhost:8080
    │
phpMyAdmin
    │
Docker Network
    │
MySQL
    │
Docker Volume
```

---

## Start the Project

```bash
docker compose -f mysql-phpmyadmin-compose.yml up -d
```

---

## Check Running Containers

```bash
docker ps
```

---

## Access phpMyAdmin

URL

```text
http://localhost:8080
```

Login

```text
Server   : db
Username : root
Password : rootpassword
```

or

```text
Server   : db
Username : db_user
Password : userpassword
```

---

## Stop the Project

```bash
docker compose -f mysql-phpmyadmin-compose.yml down
```

---

## Remove Containers and Volume

```bash
docker compose -f mysql-phpmyadmin-compose.yml down -v
```

---

## Learning Outcomes

* Docker Compose
* Multi-container Applications
* Docker Networking
* Docker Volumes
* Environment Variables
* MySQL in Docker
* phpMyAdmin Configuration

---


