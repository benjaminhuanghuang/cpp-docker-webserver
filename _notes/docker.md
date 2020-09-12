# Docker 
Coding on host machine and build in Docker container

## Create Docker box for C++
The crow microframework depends on boots

libtcmalloc for memory management

build docker image
```
  cd cppbox
  docker build -t cppbox .       # -t: tag
```

Run the bach shell on the container
-ti runs docker in terminal interactive mode
```
  docker run -ti cppbox:latest bash
```
find boost in the running container to make sure boost is installed
```
  $ find /usr -name libboost*.*
  $ exit
```

Create a volumne. Volume is the directory shared by the host machine and Docker container
Coding in host machine and build in Docker container
```
  docker run -v /Users/bhuang/ben-github/cpp-docker-webserver/cppweb:/usr/src/cppweb -ti cppbox:latest bash
```

## Access the web server running in the container
-e creates an environment variable 
```
  docker run -p <host port>:<container port> -e PORT=8080
```



## The finnal Docker commond 
- Build
```
  docker run -v /Users/bhuang/ben-github/cpp-docker-webserver/cppweb:/usr/src/cppweb -ti cppbox:latest bash
```
- Run server and open port
```
  docker run -v /Users/bhuang/ben-github/cpp-docker-webserver/cppweb:/usr/src/cppweb -p 8080:8080 -e PORT=8080  -w /usr/src/cppweb/hello_crow/build -ti cppbox:latest ./hello_crow
```
-w set working path to /usr/src/cppweb/hello_crow/build. Help the code use "../public" to access the file