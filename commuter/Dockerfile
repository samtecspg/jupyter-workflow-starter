FROM node:latest

RUN apt-get update && apt-get install -y wget
ENV DOCKERIZE_VERSION v0.6.1
RUN wget https://github.com/jwilder/dockerize/releases/download/$DOCKERIZE_VERSION/dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && tar -C /usr/local/bin -xzvf dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && rm dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz

# setup container for installation.
RUN mkdir /app
WORKDIR /app
ADD . /app

# run installation/ build commands.
RUN npm i -g @nteract/commuter

ENV HOST=0.0.0.0
ENV PORT=4000

EXPOSE 4000

CMD dockerize -wait tcp://elasticsearch:9200 -timeout 60s commuter
