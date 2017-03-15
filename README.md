# Feed-The-Beast Beyond (Minecraft 1.10.2) in a Docker Container
To pull the image:
```
docker pull audiohacked/ftb_beyond:stable
```

It's highly recommended run a data container:
```
docker run --name ftb_beyond_datastore audiohacked/ftb_beyond:stable true
```

Then, run the server container:
```
docker run --detach --interactive --tty \
    --name ftb_beyond \
    --volumes-from ftb_beyond_datastore \
    -p 25565:25565 \
    -e EULA=TRUE \
    audiohacked/ftb_beyond:stable
```
