FROM golang:1.12.4-alpine3.9

RUN apk --no-cache add curl \
  && curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl \
  && mv ./kubectl /usr/local/bin \
  && chmod 755 /usr/local/bin/kubectl \
  && apk del curl

COPY Dockerfile /cnab/Dockerfile
COPY app/run /cnab/app/run

CMD ["/cnab/app/run"]
