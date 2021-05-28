# [Dockerized Wifite based on alpine image](https://hub.docker.com/r/afsmnghr/wifite)

<https://github.com/AfsmNGhr/docker-wifite>

```sh
docker run -it --rm \
    --net host \
    --privileged \
    -v $(pwd)/work:/root \
    --workdir /root \
    afsmnghr/wifite wifite --random-mac
```

For advanced usage

```sh
docker run -it --rm \
    --net host \
    --privileged \
    -v $(pwd)/work:/root \
    --workdir /root \
    afsmnghr/wifite sh
```
