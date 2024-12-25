# Dockerfile 修正
FROM ubuntu:latest

# 必要なツールをインストール
RUN apt-get update && apt-get install -y curl bash git && \
    curl -LO https://github.com/gohugoio/hugo/releases/download/v0.111.3/hugo_extended_0.111.3_Linux-64bit.tar.gz && \
    tar -xzvf hugo_extended_0.111.3_Linux-64bit.tar.gz -C /usr/local/bin && \
    rm hugo_extended_0.111.3_Linux-64bit.tar.gz

WORKDIR /site
CMD ["/usr/local/bin/hugo"]
