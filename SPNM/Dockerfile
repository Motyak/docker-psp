# # Build the 'shell' image with Dockerfile
# docker build -t shell .

# # Run container 'shell' as a daemon using 'shell' image
# docker run --name shell -itd shell
# # Run the command 'echo hello world' inside 'shell' container
# docker exec shell echo hello world

# (5.61MB)
FROM alpine:3.13

# Install sudo, git (13.76MB)
# Install python (44.34MB)
# Install node.js + mongodb (driver) + http-server (38.98MB)
# Install node.js dev, doc and npm (28.41MB)
# Install mongodb (106.41 MB)
RUN apk add --no-cache sudo \
    && apk add --no-cache git \
    && apk add --no-cache python3 \
    && apk add --no-cache nodejs \
    && apk add --no-cache nodejs-dev \
    && apk add --no-cache nodejs-doc \
    && apk add --no-cache npm \
    && npm install -g http-server \
    && npm install -g mongodb \
    && npm link mongodb \
    && echo 'http://dl-cdn.alpinelinux.org/alpine/v3.9/main' >> /etc/apk/repositories \
    && echo 'http://dl-cdn.alpinelinux.org/alpine/v3.9/community' >> /etc/apk/repositories \
    && apk update \
    && apk add mongodb yaml-cpp=0.6.2-r2 \
    && mkdir -p /data/db

# Launch a shell
ENTRYPOINT ["sh"]