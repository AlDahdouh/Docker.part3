FROM node:alpine

ENV API_URL=http://localhost/api/
EXPOSE 5000

RUN apk add --no-cache git && \
    git clone https://github.com/docker-hy/frontend-example-docker.git && \
    apk del git && \
	adduser -D app && \
	chown -hR app /frontend-example-docker

USER app
	
WORKDIR /frontend-example-docker

RUN npm install

ENTRYPOINT ["npm"]
CMD ["start"]
