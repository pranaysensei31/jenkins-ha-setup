# Jenkins High Availability Setup

This project demonstrates a **High Availability (HA) Jenkins architecture** using Docker and Nginx. The system ensures that if the Jenkins master instance fails, traffic is automatically routed to a backup instance.

## Architecture

User → Nginx Load Balancer → Jenkins Cluster

* Jenkins Master
* Jenkins Backup
* Nginx Reverse Proxy

## Technologies Used

* Jenkins
* Docker
* Docker Compose
* Nginx
* GitHub

## System Architecture

```
                User Browser
                     │
                     ▼
             Nginx Load Balancer
                   (Port 8080)
                     │
          ┌──────────┴──────────┐
          ▼                     ▼
     Jenkins Master        Jenkins Backup
       (Port 8081)           (Port 8082)
```

## Features

* Jenkins High Availability
* Automatic Failover
* Load Balancing using Nginx
* Containerized Infrastructure using Docker

## Running the Project

Clone the repository:

```
git clone https://github.com/pranaysensei31/jenkins-ha-setup.git
cd jenkins-ha-setup
```

Start the system:

```
docker compose up -d
```

Access Jenkins:

```
http://localhost:8080
```

## Failover Demonstration

1. Open Jenkins through the load balancer.
2. Stop the Jenkins master container:

```
docker stop jenkins_master
```

3. Refresh the browser.

Traffic will automatically route to the backup Jenkins instance.

## Project Structure

```
jenkins-ha-setup
│
├── docker-compose.yml
├── nginx.conf
├── README.md
```

## Author

Pranay Mahajan
