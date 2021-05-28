# [Blackarch](https://blackarch.org) in Docker container

BlackArch Linux is an Arch Linux-based penetration testing distribution for penetration testers and security researchers.

```sh
docker run \
    -it \
    --rm \
    --privileged \
    --network host \
    -v $(pwd)/blackarch:/root \
    blackarch
```

```sh
airodump-ng \
    --manufacturer \
    --uptime \
    --wps \
    --output-format pcap \
    --ht40+ \
    -a \
    WLAN_IFACE
```
