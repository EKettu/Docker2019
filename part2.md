**Exercise 2.1**

docker-compose.yml:

version: '3.5'
services:
    backend:
      image: back1
      ports:
            - "8000:8000"
    frontend:
      image: front1
      ports:
            - "5000:5000"


**Exercise 2.2.**

docker-compose.yml:

version: '3.5'
services:
    backend:
      image: back1
      ports:
        - "8000:8000"
      environment:
        - REDIS=redis
    frontend:
      image: front1
      ports:
        - "5000:5000"
    redis:
      image: "redis:alpine"


**Exercise 2.3.**

docker-compose.yml:

version: '3.5'
services:
    backend:
      image: back1
      ports:
        - "8000:8000"
      environment:
        - REDIS=redis
        - DB_USERNAME=user1
        - DB_PASSWORD=example
        - DB_NAME=datab
        - DB_HOST=db
    frontend:
      image: front1
      ports:
        - "5000:5000"
    redis:
      image: "redis:alpine"
    db:
      image: postgres
      restart: always
      environment:
        POSTGRES_PASSWORD: example
        POSTGRES_USER: user1
        POSTGRES_DB: datab


**Exercise 2.4.**

docker-compose.yml:

version: '3.5' 

services: 
    backend: 
      build: https://github.com/docker-hy/ml-kurkkumopo-backend.git
      volumes: 
        - model:/src/model
      ports:
        - 5000:5000

    frontend: 
      build: https://github.com/docker-hy/ml-kurkkumopo-frontend.git 
      ports: 
        - '3000:3000' 
    training:
      build: https://github.com/docker-hy/ml-kurkkumopo-training.git
      volumes:
        - model:/src/model
        - data:/src/data
        - images:/src/imgs
volumes:
  model:
  data:
  images:


**Exercise 2.5.**

docker-compose.yml:

version: '3.5'
services:
    backend:
      image: back1
      ports:
        - "8000:8000"
      environment:
        - REDIS=redis
        - DB_USERNAME=user1
        - DB_PASSWORD=example
        - DB_NAME=datab
        - DB_HOST=db
    frontend:
      image: front1
      ports:
        - "5000:5000"
    redis:
      image: "redis:alpine"
    db:
      image: postgres
      restart: always
      environment:
        POSTGRES_PASSWORD: example
        POSTGRES_USER: user1
        POSTGRES_DB: datab
    nginx:
      image: nginx
      ports:
        - "80:80"
      volumes:
        - ./nginx.conf:/etc/nginx/nginx.conf



nginx.conf:

events { worker_connections 1024; }

http {
  server {
    listen 80;

    location / {
      proxy_pass http://frontend:5000/;
    }

    location /api/ {
      proxy_pass http://backend:8000/;
    }
  }
}


