# My Project

This project consists of a Laravel backend and a Vue.js frontend, both containerized using Docker, along with Adminer for database management.

## Prerequisites

- Docker
- Docker Compose

## Structure

- `backend/`: Laravel project files
- `frontend/`: Vue.js project files
- `nginx/`: Nginx configuration files
- `docker-compose.yml`: Docker Compose configuration
- `.env`: Environment variables

## Setup and Running

### 1. Clone the Repository

```bash
git clone https://github.com/Andy6440/ABMUsers.git
cd ABMUsers
```
### 2. Configure Environment Variables

Edit the  `.env` file to set up your environment variables, such as database credentials.

### 3. Build the Containers

Build the Docker containers:    
```bash
docker-compose build
```

### 4. Start the Containers
Start the containers in detached mode:
```bash
docker-compose up -d
```
### 5. Access the Application

- Frontend: Open `http://localhost:82` in your browser.
- Backend: Access the API at `http://localhost:81/api`.
- Adminer: Access the database management interface at `http://localhost:8090`.

### 6. Stopping and Removing Containers
To stop and remove the containers, run:
```bash
docker-compose down
```