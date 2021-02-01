# # Build the 'bash' image with Dockerfile
# docker build -t bash .

# # Run container 'bash' as a daemon using 'bash' image
# docker run --name bash -itd bash
# # Run the command 'echo hello world' inside 'bash' container
# docker exec bash echo hello world

FROM alpine:3.13

RUN apk add --no-cache bash \
    && apk add --no-cache sudo \
    && apk add --no-cache git \
    && apk add --no-cache curl \
    && apk add --no-cache grep \
    && apk add --no-cache perl \
    && apk add --no-cache php7 \
    && apk add --no-cache sqlite

ENTRYPOINT ["bash"]