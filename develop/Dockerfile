# crowleyio/develop
# For more information: http://github.com/crowley-io/docker
#
# develop
#
# Example :
#   docker run --rm -it crowleyio/develop /bin/bash

# VERSION 0.1.0

FROM buildpack-deps:wheezy-scm

MAINTAINER november-eleven

ENV DEBIAN_FRONTEND noninteractive
ENV GOLANG_VERSION 1.4.1
ENV GOLANG_SHA256 66665005fac35ba832ff334977e658f961109d89a7a2358ae7707be0efb16fca
ENV NODE_VERSION 0.10.36
ENV NODE_SHA256 2bc13477684a9fe534bdc9d8f4a8caf6257a11953b57c42cad9b919ee259a0d5
ENV NPM_VERSION 2.5.0
ENV PATH /app/bin:/usr/local/go/bin:$PATH

RUN apt-get update && apt-get upgrade -y \
	&& apt-get install -y gcc libc6-dev make --no-install-recommends \
	&& apt-get --purge autoremove -y \
	&& apt-get clean all \
	&& rm -rf /var/lib/apt/lists/*

# install go
RUN curl -SLO "https://golang.org/dl/go$GOLANG_VERSION.src.tar.gz" \
	&& echo "$GOLANG_SHA256  go$GOLANG_VERSION.src.tar.gz" | sha256sum -c - \
	&& tar -xzf go$GOLANG_VERSION.src.tar.gz -C /usr/local \
	&& rm go$GOLANG_VERSION.src.tar.gz \
	&& cd /usr/local/go/src && ./make.bash --no-clean 2>&1

# install nodejs
RUN curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION-linux-x64.tar.gz" \
	&& echo "$NODE_SHA256  node-v$NODE_VERSION-linux-x64.tar.gz" | sha256sum -c - \
	&& tar -xzf "node-v$NODE_VERSION-linux-x64.tar.gz" -C /usr/local --strip-components=1 \
	&& rm "node-v$NODE_VERSION-linux-x64.tar.gz" \
	&& npm install -g npm@"$NPM_VERSION" \
	&& npm cache clear

RUN mkdir -p /app/src
ENV GOPATH /app
WORKDIR /app