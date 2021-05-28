FROM archlinux:latest

# ARG LOGIN=${USER:-user}
# ARG UID=$(id -u $USER)
# ARG GID=$(id -g $USER)

# ENV LOGIN=${LOGIN}
# ENV UID=${UID}
# ENV GID=${GID}

COPY ./pacman.conf /etc/pacman.conf

RUN set -ex; \
    \
    export TERM=xterm; \
    curl \
        --location \
        --silent \
        --show-error \
        https://blackarch.org/strap.sh | bash

RUN set -ex; \
    \
    pacman \
        --sync \
        --refresh \
        --sysupgrade \
        --needed \
        --noconfirm \
            bash-completion \
            git \
            mc \
            screen \
            sudo \
            wget \
            which \
            xterm \
        \
            pocl \
            usbutils \
        \
            aircrack-ng \
            cowpatty \
            crunch \
            bully \
            john \
            hashcat \
            hashcatch \
            hcxdumptool \
            hcxtools \
            macchanger \
            mdk3 \
            mdk4 \
            pixiewps \
            pyrit \
            reaver \
            scapy \
            wifite \
            wireshark-cli \
    ; \
    airodump-ng-oui-update; \
    find / \
        -type f \
        '(' -name '*.pacnew' -or \
        -name '*.pacsave' ')' \
        -delete 2> /dev/null

COPY ./sudoers /etc/sudoers

RUN set -ex; \
    \
    groupadd --gid $GID $LOGIN; \
    useradd --uid $UID -


CMD ["bash", "-i"]
