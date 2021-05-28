# [Cloud9](https://github.com/c9/core)

Cloud9 is a complete web based IDE with terminal access. This container is for running their core SDK locally and developing plugins.

[linuxserver/cloud9](https://docs.linuxserver.io/images/docker-cloud9)

```sh
docker run -d \
  --name=cloud9 \
  -e PUID=1000 \
  -e PGID=1000 \
  -e TZ=Europe/London \
  -e GITURL=https://github.com/linuxserver/docker-cloud9.git `#optional` \
  -e USERNAME= `#optional` \
  -e PASSWORD= `#optional` \
  -p 8000:8000 \
  -v /path/to/your/code:/code `#optional` \
  -v /var/run/docker.sock:/var/run/docker.sock `#optional` \
  --restart unless-stopped \
  ghcr.io/linuxserver/cloud9
```

## Running on a [Heroku](https://www.heroku.com) container stack

```sh
CLOUD9_IMAGE_VARIANT=latest
HEROKU_APP_NAME=cloud9-${CLOUD9_IMAGE_VARIANT}
```

```sh
heroku apps:create \
    --stack container \
    --region ${HEROKU_REGION:-eu} \
    ${HEROKU_APP_NAME}
```

```sh
heroku config:set \
    --PUID=${PUID:-1000} \
    --PGID=${PGID:-1000} \
    ${HEROKU_APP_NAME}
```

```sh
heroku container:login
# Push Dockerfile to web process type
heroku container:push web
# Releases the previously pushed web process type
heroku container:release web
```
