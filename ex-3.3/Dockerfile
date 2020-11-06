FROM ubuntu:latest


RUN apt-get update && \
    apt-get install -y apt-transport-https ca-certificates curl gnupg-agent software-properties-common && \
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | apt-key add - && \
    add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu  $(lsb_release -cs)  stable" && \
    apt-get update && \
    apt-get install docker-ce docker-ce-cli containerd.io -y && \
    curl -L "https://github.com/docker/compose/releases/download/1.27.4/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose && \
    chmod +x /usr/local/bin/docker-compose && \
    apt-get purge -y --auto-remove curl && \
    rm -rf /var/lib/apt/list/*

COPY  ./docker-compose.yml ./docker-compose.yml

CMD docker login -u ${DOCKER_USER} -p ${DOCKER_PASSWORD}; docker-compose build  ; docker-compose push