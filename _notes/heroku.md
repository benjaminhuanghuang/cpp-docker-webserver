Heroku is a fully managed container-based cloud platform


## Install heroku CLI
```
  brew install heroku/brew/heroku

  heroku --version
```


## Deploy Docker container to Heroku
1. Containerize our app
```
  docker ps    # list all running container, find the id of the container

  docker cp . <dockerId>:/usr/src/cppweb

  docker commit <dockerId> hello_crow:latest     # commit changes to hello_crow

  create Dockerfile under hello_crow folder

  cd hello_crow and login Heroku
```
2. Heroku login
```
  heroku login
  heroku container:login

```

3. Create Heroku app
```
  heroku create             # create app
```
damp-hollows-53557
https://damp-hollows-53557.herokuapp.com/ | https://git.heroku.com/damp-hollows-53557.git

4. Push the container and release it.
```
  docker build -t hello_crow .                           # build a Docker image
  heroku container:push web -a damp-hollows-53557        # push Docker image to app

  heroku container:release web -a damp-hollows-53557 
```
5. Test in the brower
```
  heroku open -a damp-hollows-53557 
```