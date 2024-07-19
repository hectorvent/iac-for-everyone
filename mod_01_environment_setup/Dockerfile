FROM debian:12-slim

## HACK Install ansible
ENV UBUNTU_CODENAME=jammy

RUN apt update \
    && apt install -yqq openssh-server curl wget \
    && curl --proto '=https' --tlsv1.2 -fsSL https://get.opentofu.org/install-opentofu.sh -o install-opentofu.sh \
    && chmod +x install-opentofu.sh \
    && ./install-opentofu.sh --install-method deb \
    && rm install-opentofu.sh \
    && wget -O- "https://keyserver.ubuntu.com/pks/lookup?fingerprint=on&op=get&search=0x6125E2A8C77F2818FB7BD15B93C4A3FD7BB9C367" | gpg --dearmour -o /usr/share/keyrings/ansible-archive-keyring.gpg \
    && echo "deb [signed-by=/usr/share/keyrings/ansible-archive-keyring.gpg] http://ppa.launchpad.net/ansible/ansible/ubuntu $UBUNTU_CODENAME main" | tee /etc/apt/sources.list.d/ansible.list \
    && apt update && apt install -yqq ansible \
    && wget https://github.com/digitalocean/doctl/releases/download/v1.104.0/doctl-1.104.0-linux-amd64.tar.gz \
    && tar xf doctl-1.104.0-linux-amd64.tar.gz \
    && mv doctl /usr/local/bin \
    && apt clean && rm -rf doctl-1.104.0-linux-amd64.tar.gz 