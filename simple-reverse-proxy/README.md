# Simple Reverse Proxy (Run on Docker)

# Requires

- Docker 

# Steps

### 1. Clone

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

### 3. Create Web Server

3.1 Build Docker Image

```sh
$ cd web
$ docker build -t simple-web-server .  
$ docker images 
```

3.2 Run Container 

```sh
$ docker run -d -p 3002:80 --name simple-web-server --restart=always simple-web-server 
$ docker ps -a 
```

3.3 Test

> http://<HOST_NAME or IP>:3002


### 4. Create Reverse Proxy 

4.1 Build Docker Image

```sh
$ cd reverse-proxy 
$ docker build -t simple-reverse-proxy .  
$ docker images 
```

4.2 Run Container 

```sh
$ docker run -d -p 80:80 --name simple-reverse-proxy --restart=always --link=simple-api-server --link=simple-web-server simple-reverse-proxy 
$ docker ps -a 
```

4.3 Test

> http://<HOST_NAME or IP>
