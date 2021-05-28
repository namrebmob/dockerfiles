# Lightweight headless [Kali Linux](https://www.kali.org) image

Only tools included that doesn't require GUI

```sh
docker run \
    -it \
    --rm \
    --privileged \
    --name kalilinux-headless \
    --network host \
    --volume db:/var/lib/postgresql/data \
    --volume $(pwd)/kali:/root \
    kalilinux-headless /bin/bash
```

To use postgres db with metasploit:

```sh
service postgresql start
msfdb init
```
