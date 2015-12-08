# crowleyio/go-packer
# For more information: http://github.com/crowley-io/docker
#
# go-packer
#
# Example :
#   docker run --rm -it crowleyio/go-packer

# VERSION 0.1.0

FROM golang:1.5.2

MAINTAINER november-eleven

RUN apt-get --purge autoremove -y \
	&& apt-get clean all \
	&& rm -rf /var/lib/apt/lists/* \
	&& go get -u github.com/golang/lint/golint

ADD pack /usr/local/bin/
RUN chmod +x /usr/local/bin/pack
CMD ["/usr/local/bin/pack"]
