# keepalivedのDockerfile
FROM ubuntu:latest

# 必要なパッケージをインストール
RUN apt-get update && apt-get install -y \
    keepalived \
    ipvsadm \
    iproute2 \
    iputils-ping \
    curl \
    iptables \
    tcpdump \
    --no-install-recommends && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Keepalivedのすべてのファイルをコピー
COPY . /etc/keepalived

# Keepalivedをエントリーポイントとして起動
CMD ["keepalived", "-n", "-l", "-D"]

