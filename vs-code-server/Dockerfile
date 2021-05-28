FROM codercom/code-server

USER root

RUN apt-get update && \
	apt-get install --no-install-recommends --yes \
		bash-completion \
		python3-venv \
		python3-pip && \
    curl -Ls https://api.github.com/repos/cli/cli/releases/latest | \
    grep -wo "https.*amd64.deb" | xargs curl -Lo /tmp/gh_latest.deb && \
    dpkg -i /tmp/gh_latest.deb && \
    apt-get clean && rm -rf /tmp/* /var/tmp/*
