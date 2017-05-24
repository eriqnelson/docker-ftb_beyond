# Feed-The-Beast Beyond (Minecraft 1.10.2) in a Docker Container
To pull the image:
```
docker pull eriqnelson/docker-ftb_beyond:latest
```

It's highly recommended run a data container:
```
docker run --name ftb_beyond_datastore eriqnelson/docker-ftb_beyond:latest true
```

Then, run the server container:
```
docker run --detach --interactive --tty \
    --name ftb_beyond \
    --volumes-from ftb_beyond_datastore \
    -p 25565:25565 \
    -e EULA=TRUE \
    eriqnelson/docker-ftb_beyond:latest
```
