FROM ubuntu:noble
ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get -y update && apt-get -y upgrade && apt-get -y install dnscrypt-proxy ca-certificates
WORKDIR /app
COPY ./config.toml ./
EXPOSE 55
CMD ["dnscrypt-proxy", "-config", "./config.toml"]
