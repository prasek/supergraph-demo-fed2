FROM --platform=linux/amd64 debian:bullseye

RUN apt-get update && apt-get install -y \
    ca-certificates \
    curl 

WORKDIR /dist

COPY ./target/release/acme_router/ router

# for faster docker shutdown
STOPSIGNAL SIGINT

# set the startup command to run your binary
# note: if you want sh you can override the entrypoint using docker run -it --entrypoint=sh my-router-image
ENTRYPOINT ["./router"]
