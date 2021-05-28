FROM kalilinux/kali-rolling

RUN set -ex; \
    \
    DEBIAN_FRONTEND=noninteractive; \
    apt-get update && apt-get install --no-install-recommends --yes \
        # metapackage kali-linux-headless: Default install that doesn't require GUI
        kali-linux-headless \
        # common system tools
        bash-completion \
        pciutils \
        lsof \
        # net
        arping \
        arp-scan \
        iputils-ping \
        iputils-arping \
        iputils-tracepath \
        iproute2 \
        tor \
        hping3 \
        # files tools
        binwalk \
        bulk-extractor \
        pdfcrack \
        magicrescue \
        # DNS Enumeration and Network Mapping
        dns2tcp \
        dnschef \
        dnsenum \
        dnsrecon \
        nmap \
        netcat \
        hydra \
        # fast subdomains enumeration tool for penetration testers
        sublist3r \
        # python tool designed to enumerate subdomains on a target domain
        knockpy \
        smtp-user-enum \
        enum4linux \
        # exploitation tools
        routersploit \
        exploitdb \
        # password attacks
        crunch \
        hcxtools \
        hcxdumptool \
        hashid \
        hashcat \
        hashcat-utils \
        # contains the rockyou wordlist
        wordlists \
        # wireless attacks
        aircrack-ng \
        bully \
        pyrit \
        mdk4 \
        ; \
        \
        airodump-ng-oui-update; \
        apt-get clean && apt-get autoremove; \
        rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* ~/.cache

VOLUME /var/lib/postgresql/data
