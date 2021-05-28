FROM alpine:edge

ARG UID=${UID:-1000}
ARG GID=${GID:-1000}
ARG USER=${USER}

RUN set -ex; \
    echo "https://dl-cdn.alpinelinux.org/alpine/edge/testing" >> /etc/apk/repositories; \
    apk add --no-cache --upgrade --virtual buildDeps \
        git \
        build-base \
        \
        libpcap-dev \
    ; \
    \
    apk add --no-cache --upgrade \
        python3 \
        \
    # Information Gathering
        # DNS
        dnsenum \
        dnsrecon \
        dnstracer \
        dnstop \
        # Scanners
        nmap-nping \
        arp-scan \
        arping \
        dhcp-probe \
        scanssh \
        # zmap \
    # Wireless Attacks
        aircrack-ng \
        pixiewps \
        reaver-wps-fork-t6x \
        kismet-linux-wifi \
    # Monitoring
        arpwatch \
        bpfmon \
        darkstat \
        iftop \
        nethogs \
    # Sniff, analyze, spoof
        hexinject \
        hping3 \
        httpry \
        ngrep \
        p0f \
        rtpengine \
        sniffglue \
        tcpflow \
        # Sip
        sngrep \
        sipp \
        sipgrep \
        tcpdump \
        ssldump \
        tcptraceroute \
        tcpreplay \
        tshark \
    ; \
    \
    # # bully
    # git clone https://github.com/aanarchyy/bully; \
    # cd bully*/src && make install && cd && rm -rf bully; \
