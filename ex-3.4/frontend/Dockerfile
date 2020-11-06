FROM ubuntu:latest

ENV API_URL=http://localhost/api/
EXPOSE 5000

RUN apt-get update && apt-get install curl -y  && \
    curl -sL https://deb.nodesource.com/setup_10.x | bash && \
    apt-get install nodejs git-core -y && \
    git clone https://github.com/docker-hy/frontend-example-docker.git && \
    apt-get purge -y --auto-remove curl git && \
    rm -rf /var/lib/apt/list/* && \
	useradd -m app && \
	chown -hR app /frontend-example-docker

USER app
	
WORKDIR /frontend-example-docker

RUN npm install

ENTRYPOINT ["npm"]
CMD ["start"]
