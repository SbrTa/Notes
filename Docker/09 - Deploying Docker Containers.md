# Deploying Docker Containers
  - Bind mounts shoudn't be used in production

### Production deployment
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
    
