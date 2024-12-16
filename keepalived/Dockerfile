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
    iptables-persistent \
    --no-install-recommends && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Keepalivedのすべてのファイルをコピー
COPY . /etc/keepalived

# IPフォワードを有効にする設定
RUN echo "net.ipv4.ip_forward=1" >> /etc/sysctl.conf && \
    sysctl -p

# Keepalivedをエントリーポイントとして起動
CMD ["keepalived", "-n", "-l", "-D"]
