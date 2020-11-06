FROM node:alpine as build-stage

ENV API_URL=http://localhost/api/
EXPOSE 5000

RUN apk add --no-cache git && \
    git clone https://github.com/docker-hy/frontend-example-docker.git && \
    apk del git 
	
WORKDIR /frontend-example-docker

RUN npm install --save-dev webpack && \
    npm run build 

FROM nginx:alpine

COPY --from=build-stage /frontend-example-docker/dist/ /usr/share/nginx/html
