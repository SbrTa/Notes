# Docker

2023-01-16 (01 - Getting Started - All)
  - What is Docker?
  - What is Container?
  - Virtual machine vs Docker container.
  
2023-01-17 (02 - Getting Started - [001-010])
  - What is Docker Image?
  - Docker Image vs Docker Container?
  - ```
      FROM node
      WORKDIR /app
      COPY package.json /app
      RUN npm install
      COPY  . /app
      EXPOSE 80
      CMD ["node", "server.js"]
    ```
  - ```
      docker build
      docker run -p 80:80 id
      docker ps
      docker ps -a
      docker stop name
    ```
  - Layers in images
  
