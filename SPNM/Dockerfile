# # Build the 'shell' image with Dockerfile
# docker build -t shell .

# # Run container 'shell' as a daemon using 'shell' image
# docker run --name shell -itd shell
# # Run the command 'echo hello world' inside 'shell' container
# docker exec shell echo hello world

FROM alpine:3.13

COPY entrypoint.sh /entrypoint.sh

RUN apk add --no-cache sudo \
    && apk add --no-cache git \
    && apk add --no-cache python3 \
    && apk add --no-cache nodejs \
    && apk add --no-cache nodejs-dev \
    && apk add --no-cache npm \
    && npm install -g http-server \
    && npm install -g mongodb \
    && npm link mongodb \
    && echo 'http://dl-cdn.alpinelinux.org/alpine/v3.9/main' >> /etc/apk/repositories \
    && echo 'http://dl-cdn.alpinelinux.org/alpine/v3.9/community' >> /etc/apk/repositories \
    && apk update \
    && apk add mongodb yaml-cpp=0.6.2-r2 \
    && mkdir -p /data/db \
    && chmod +x /entrypoint.sh

ENTRYPOINT ["/entrypoint.sh"]