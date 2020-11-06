FROM node:alpine

ENV FRONT_URL=http://localhost/
EXPOSE 8000
RUN    apk add --no-cache git && \
       git clone https://github.com/docker-hy/backend-example-docker.git && \
       apk del git && \
	   adduser -D app && \
	   chown -hR app /backend-example-docker

USER app

WORKDIR /backend-example-docker

RUN npm install

ENTRYPOINT ["npm"]
CMD ["start"]
