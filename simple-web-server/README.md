# Simple Web Server (Run on Docker)

# Requires

- Docker 

### 1. Clone 

```sh
$ git clone https://github.com/jittagornp/nginx-example.git
$ cd nginx-example
```

### 2. Build Docker Image 

```sh 
$ cd simple-web-server
$ docker build -t simple-web-server .  
$ docker images 
```

### 3. Run Container 

```sh
$ docker run -d -p 80:80 --name simple-web-server --restart=always simple-web-server 
$ docker ps -a 
```

### 4. Test

> http://<HOST_NAME or IP>
