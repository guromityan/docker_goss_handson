FROM ubuntu:18.04

WORKDIR /root

# SSH Settings
COPY ./test-target-key /root/.ssh/
COPY ./config /root/.ssh/
# Install common tools
RUN apt update && apt install --yes curl vim
# Install ansible
RUN apt install --yes software-properties-common && \
    apt-add-repository --yes --update ppa:ansible/ansible && \
    apt install --yes ansible
# Install Goss
RUN curl -L https://github.com/aelsabbahy/goss/releases/latest/download/goss-linux-amd64 -o /usr/local/bin/goss && \
    chmod +rx /usr/local/bin/goss && \
    cp -i $(which goss) .

CMD ["tail", "-f", "/dev/null"]

