## Save Container to Docker Hub

1. Login to Docker Hub
```
  docker login --username=******
```

2. Tag the image
```
  docker iamges    # find the image id
  docker tag <imageId>    ben/hello_crow:latest
```
3. Push the image.
```
  docker push ben/hello_crow
```
4. Verify the push.
```
  go to hub.docker.coms
```
