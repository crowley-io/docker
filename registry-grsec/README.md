# Docker Registry

### Introduction

This docker image provide a [Docker registry](https://hub.docker.com/_/registry/) for **[grsecurity](https://grsecurity.net/)** kernel.

It uses the **PaX exceptions** in order to mark the application as "trusted" in order to works perfectly. The exceptions are handled using _extended attributes of filesystem objects_.

> **NOTE:** This image only disable the `MPROTECT` feature.

### Installation & Usage

1. Install [Docker](https://www.docker.io/).

2. Download [trusted build](https://hub.docker.com/r/crowleyio/registry-grsec/) from public [Docker Registry](https://hub.docker.com/): `docker pull crowleyio/registry-grsec`

### Usage

Use this image as a standard registry vanilla image.
If you don't know how to use this image, please follow the [Official Documentation](https://hub.docker.com/_/registry/).

### Bugs / Contributing

**Any kind of feedback is highly appreciated !**

Make contributions the usual way through [GitHub](https://github.com/crowley-io/docker), request changes and ask questions in comments below.

### Version

* **registry:** 2.3.0
