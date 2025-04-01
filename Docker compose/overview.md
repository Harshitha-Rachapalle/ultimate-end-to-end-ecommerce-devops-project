# Docker compose

Docker Compose is a tool that allows you to define and run multi-container Docker applications using a simple YAML configuration file (docker-compose.yml).

Instead of running multiple docker run commands manually, Docker Compose lets you orchestrate everything with one command.

## 📌 Why Use Docker Compose?
🛠 **Easier Management:** Define multiple services (containers) in one file.

⚡**Simplifies Multi-Container Apps:** Run databases, backend, and frontend together.

📝**Declarative Configuration:** Define all settings in docker-compose.yml.

🔄 **Reproducibility:** Ensures consistent environments across development, testing, and production.

### The  main components of docker-compose.yml is

Services

Networks

Volume

**Key       	Description**
version	      Specifies the Compose file format (latest is 3.8)

services  	  Defines containers (like web, database)

image	        Specifies the Docker image to use

ports	Maps    container ports to host machine

environment	  Defines environment variables for containers

volumes	      Persists data between container restarts

depends_on  	Ensures service order (e.g., database starts before the web app)


# Useful Docker Compose Commands

**Command	                  Description**
docker-compose up	          Starts containers defined in docker-compose.yml

docker-compose up -d      	Runs containers in the background

docker-compose down        	Stops and removes containers, networks, and volumes

docker-compose ps          	Lists running containers

docker-compose logs	        Shows logs of all services

docker-compose restart    	Restarts all services

docker-compose exec <service> <command>	     Runs a command inside a running container


