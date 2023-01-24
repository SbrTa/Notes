# Building Multi-Container Applications with Docker
  - Create network. ```docker network create mynet```
  - Run mongodb under ```mynet```. ```docker run -d --rm --network mynet --name mydb mongo```
  - Set ```mydb`` as domain name in code base, since server and db will be under same docker network. So, they will communicate by their container name.
  - Build backend image. ```docker build -t mybackendimage .```
  - Run backend container under ```mynet``` and expose port 80 to localhost. We expose server port 80 to localhost port 80, because our front end will access backend through local machine. Frontend is in react. React runs on local machines browser, so even if react app runs under ther same network as backend, it can't communicate backend via container name. ```docker run -d --rm -p 80:80 --network mynet --name mybackend mybackendimage```
  - Set ```localhost``` as domain name in code base, since frontend will communicate server via local machine.
  - Build frontend image. ```docker build -t myfrontendimage .```
  - Run backend container under ```mynet``` and expose port 3000. Also run it in interactive mode, because interactive mode is mandatory for react app. ```docker run -d -it --rm -p 3000:3000 --network mynet --name myfrontend myfrontendimage```
