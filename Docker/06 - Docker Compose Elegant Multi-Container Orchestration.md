# Docker Compose Elegant Multi-Container Orchestration

### Docker Compose
  - A tool that allows you to replace multiple docker build, run, start, stop commands with just one configuration file.
  - Docker compose works alongside Dockerfile
  - Not suitable for managing containers in different host.
  - CMD
    ```
      docker-compose build
      docker-compose up -d
      docker-compose up -d --build
      docker-compose down
    ```
  - Demo project: https://github.com/SbrTa/Notes/blob/main/Docker/code/006-A.zip
  - Here is the docker compose file for the demo project
    ```
      version: '3.8'
      services:
        mongodb:
          image: 'mongo'
          container_name: mongodb
          volumes:
            - data:/data/db
          env_file:
            - ./env/mongo.env
        backend:
          build:
            context: ./backend
            dockerfile: Dockerfile
          container_name: backend
          ports:
            - '80:80'
          volumes:
            - ./backend:/app 
            - logs:/app/logs 
            - /app/node_modules
          env_file:
            - ./env/backend.env
          depends_on:
            - mongodb
        frontend:
          build: 
            context: ./frontend
            dockerfile: Dockerfile
          container_name: frontend
          ports:
            - '3000:3000'
          volumes:
            - ./frontend/src:/app/src
          stdin_open: true
          tty: true
          depends_on:
            - backend
      volumes:
        data:
        logs:
    ```
