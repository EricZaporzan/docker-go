FROM golang:1.8-alpine
RUN apk update && apk upgrade && \
    apk add --no-cache bash git openssh && \
    apk add --no-cache nodejs=6.9.5-r1 && \
    npm install -g yarn

RUN mkdir -p /go/src/app
WORKDIR /go/src/app

COPY build.sh /usr/local/bin/build

RUN chmod +x /usr/local/bin/build \
  && go get github.com/Masterminds/glide \
  && echo "nobody:x:1:1:nobody:/:/bin/sh" >> /etc/passwd \
  && echo "nobody:x:1:" >> /etc/group
