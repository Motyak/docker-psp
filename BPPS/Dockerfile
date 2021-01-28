# # Build the 'bash' image with Dockerfile
# docker build -t bash .

# # Run container 'bash' as a daemon using 'bash' image
# docker run --name bash -itd bash
# # Run the command 'echo hello world' inside 'bash' container
# docker exec bash echo hello world

# (5.61MB)
FROM alpine:3.13

# Install bash + man pages + autocompletion packages (6.03MB)
# Install sudo, build-base, git, curl, grep, perl packages (45.24MB)
# Install PHP package (3.92 MB)
# Install SQLite package (1.16MB)
RUN apk add --no-cache bash \
    && apk add --no-cache bash-completion \
    && apk add --no-cache bash-doc \
    && apk add --no-cache sudo \
    && apk add --no-cache build-base \
    && apk add --no-cache git \
    && apk add --no-cache curl \
    && apk add --no-cache grep \
    && apk add --no-cache perl \
    && apk add --no-cache php7 \
    && apk add --no-cache sqlite

# Launch a bash
ENTRYPOINT ["bash"]