FROM grababyte/alpine-base:0.7.5

LABEL devops.grababyte.image.authors="GrabAByte"

ENV GO_PATH="/opt/go"
ENV PATH="$PATH:$GO_PATH:/usr/local/go/bin"
ENV GO_VERSION="1.18.2"

RUN \
  apk add --no-cache go==1.16.15-r0 && \
  rm -rf /var/cache/apk/* && \
  curl https://dl.google.com/go/go"${GO_VERSION}".src.tar.gz -o go"${GO_VERSION}".src.tar.gz && \
  tar -C /usr/local -xvf go"${GO_VERSION}".src.tar.gz && \
  rm -f go"${GO_VERSION}".src.tar.gz

WORKDIR /usr/local/go/src

RUN ./make.bash

CMD ["go", "version"]
