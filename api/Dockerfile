FROM ubuntu
WORKDIR /docker-compose/docker-compose-ci/api
USER root
RUN apt update
RUN apt install -y curl git netcat
RUN curl -sL https://deb.nodesource.com/setup_12.x | bash -
RUN apt-get install -y nodejs
RUN apt-get install -y build-essential
WORKDIR /docker-compose/docker-compose-ci/api/poolmanager-api
COPY . .
RUN npm install 
RUN npm build
EXPOSE 8080
COPY entrypoint.sh .
ENTRYPOINT ["./entrypoint.sh"]
