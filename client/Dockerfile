# client用のDockerfile

FROM ubuntu:latest

# 必要なパッケージをインストール
RUN apt-get update && apt-get install -y \
    curl \
    iputils-ping \
    tcpdump \
    --no-install-recommends && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*
