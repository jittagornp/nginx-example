# Simple Reverse Proxy (Run on Docker)

# Requires

- Docker 

# Steps

### 1. 

```sh
$ git clone https://github.com/jittagornp/nginx-example.git
$ cd nginx-example
$ cd simple-reverse-proxy 
```

### 2. Create API Server

2.1 Build Docker Image

```sh
$ cd api
$ docker build -t simple-api-server .  
$ docker images 
```

2.2 Run Container 

```sh
$ docker run -d -p 3001:80 --name simple-api-server --restart=always simple-api-server 
$ docker ps -a 
```

2.3 Test

> http://<HOST_NAME or IP>:3001
