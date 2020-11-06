FROM ubuntu:latest

ENV FRONT_URL=http://localhost/
EXPOSE 8000
RUN    apt-get update && apt-get install curl -y && \
       curl -sL https://deb.nodesource.com/setup_10.x | bash && \
       apt-get install nodejs git-core -y && \
       git clone https://github.com/docker-hy/backend-example-docker.git && \
       apt-get purge -y --auto-remove curl git && \
       rm -rf /var/lib/apt/list/*

WORKDIR /backend-example-docker

RUN npm install

ENTRYPOINT ["npm"]
CMD ["start"]
