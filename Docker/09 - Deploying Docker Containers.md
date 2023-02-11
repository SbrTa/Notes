# Deploying Docker Containers
  - Bind mounts shoudn't be used in production
  - Multicontainer projects might need to be split
  - Trade offs between control and responsibility
  - Docker compose is not great for production deployment

### Production deployment (Manually)
  - Create image on locale machine
  - Push it to Docker repository, ie - Dockerhub
  - Install and run docker in server
  - Pull image from repository
  - Run container
  - Update:
    - Create updated image
    - Push to repository
    - Pull from server
    - Re run container
    
### AWS ECS (Elastic Container Service)
  - Container defination
  - Task defination
  - Service
  - Cluster

### Multi stage docker file
Docker file
  ```
      // Stage 1
      FROM node:14-alpine ans build
      WORKDIR /app
      COPY package.json /app
      RUN npm install
      COPY  . .
      RUN npm run build
      
      // Stage 2
      FROM nginx:stable-alpine
      COPY --from=build /app/build /usr/share/nginx/html
      EXPOSE 80
      CMD ["nginx", "-g", "daemon off;"]
      
  ```

