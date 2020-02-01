FROM golang:1.13-alpine3.11

RUN apk add bash git make --update --no-cache && \
    go get -u golang.org/x/lint/golint && \
    mkdir /app && \
    chmod 777 /app

WORKDIR /app
