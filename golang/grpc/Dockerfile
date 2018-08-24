# Dockerfile for gRPC Golang
FROM golang:1.10.3-alpine3.8

ENV PB_VER 3.1.0
ENV PB_URL https://github.com/google/protobuf/releases/download/v${PB_VER}/protoc-${PB_VER}-linux-x86_64.zip

RUN apk add --no-cache --virtual .build-deps curl git && \
    mkdir -p /tmp/protoc && \
    curl -L ${PB_URL} > /tmp/protoc/protoc.zip && \
    cd /tmp/protoc && \
    unzip protoc.zip && \
    cp /tmp/protoc/bin/protoc /usr/local/bin && \
    cp -R /tmp/protoc/include/* /usr/local/include && \
    chmod go+rx /usr/local/bin/protoc && \
    cd /tmp && \
    rm -r /tmp/protoc && \
    go get google.golang.org/grpc && \
    go get github.com/golang/protobuf/protoc-gen-go && \
    apk del .build-deps
