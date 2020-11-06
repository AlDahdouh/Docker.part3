FROM ubuntu:latest


RUN apt-get update && apt-get install curl -y  && \
    curl -sL https://deb.nodesource.com/setup_10.x | bash && \
    apt-get install nodejs -y && \
    apt-get purge -y --auto-remove curl  && \
    rm -rf /var/lib/apt/list/*

WORKDIR /app
COPY . .

RUN npm install

ENTRYPOINT ["npm"]
CMD ["start"]