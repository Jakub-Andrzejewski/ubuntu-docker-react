# ubuntu-docker-react

* If you are not a root user, or do not have a root priviliges, remember to do each command with ```sudo```.

## Installation

### Prepare system
- Update packages and repositories <br>
``` apt update```

- Check if you have 'curl' command installed <br>
```curl```

- If not install it <br>
```apt install curl```


### Docker
- Install Docker packages <br>
```apt install docker.io ```

- Start Docker service <br>
```systemctl start docker```

- Enable Docker to run on system startup <br>
```systemctl enable docker```

### Docker-compose
- Download latest version of docker-compose <br>
```curl -L "https://github.com/docker/compose/releases/download/1.24.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose```

- Change permisions to allow docker-compose to be executed <br>
```chmod +x /usr/local/bin/docker-compose```

### Node.js and npm
- Install node.js <br>
```apt install nodejs```

- Install npm <br>
```apt install npm```

### Npm packages
- Install create-react-app <br>
```npm install -g create-react-app```

- Install express <br>
```npm install -g express```

## Docker useful commands

### Docker itself
- List all images <br>
```docker images```
- Remove image <br>
```docker rmi <image-name/image-id>```
- Remove container <br>
```docker rm <container-name/container-id>```
- List containers <br>
```docker ps```
- Build an image from the Dockerfile <br>
```docker build -t <name> .```
- Run container out of image (-p flag is a port mapping)<br>
```docker run -p 3000:3000 <name>```
- Stop the container
```docker pause <name>```

### Docker-compose
- Build services <br>
```docker-compose build```

- Create and start services <br>
```docker-compose up```

- Stop services <br>
```docker-compose down```

## Dockerfile structure
```
FROM <image>

WORKDIR <src>

COPY <filesFromParent> <toContainer>

RUN <command>

EXPOSE <port>

CMD <command>

ENV <key=variable>
```
## Docker-compose file structure
```
version: 'x'

services:
 service1:
  build:
   contest: ./src
  ports:
   - "<port>:<port>"
  volumes:
  - <
  
```
