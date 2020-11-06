FROM node:alpine

RUN apk add --no-cache git && \
    git clone https://AlDahdouh:XXXXXXXXX@github.com/AlDahdouh/EduStatsPro.git && \
    apk del git && \
	adduser -D app && \
	chown -hR app /EduStatsPro

USER app
	
WORKDIR /EduStatsPro

RUN npm install

ENTRYPOINT ["npm"]
CMD ["start"]
