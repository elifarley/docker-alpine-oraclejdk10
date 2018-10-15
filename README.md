[![Docker Stars](https://img.shields.io/docker/stars/elifarley/docker-alpine-oraclejdk10.svg?style=flat-square)](https://hub.docker.com/r/elifarley/docker-alpine-oraclejdk10/)
[![Docker Pulls](https://img.shields.io/docker/pulls/elifarley/docker-alpine-oraclejdk10.svg?style=flat-square)](https://hub.docker.com/r/elifarley/docker-alpine-oraclejdk10/)


OracleJDK 10 Docker image
========================

This image is based on Alpine Linux image, which is only a 5MB image, and contains
[OracleJDK 10](http://www.oracle.com/technetwork/java/javase/overview/index.html).

JDK bundle contains lots of unnecessary for Docker image stuff, so it was cleaned up. There are 3
tags: `full` (only src tarballs get removed), `cleaned` (desktop parts get cleaned), `slim`
(everything but compiler and jvm is removed). `master` branch refers to `slim` tag, but `latest`
tag points to `cleaned`.

`slim` (`master` branch) image size is:

[![](https://badge.imagelayers.io/elifarley/docker-alpine-oraclejdk10:slim.svg)](https://imagelayers.io/?images=elifarley/docker-alpine-oraclejdk10:slim 'Get your own badge on imagelayers.io')

`cleaned` (`latest` tag) image size is:

[![](https://badge.imagelayers.io/elifarley/docker-alpine-oraclejdk10:cleaned.svg)](https://imagelayers.io/?images=elifarley/docker-alpine-oraclejdk10:cleaned 'Get your own badge on imagelayers.io')

`full` image size is:

[![](https://badge.imagelayers.io/elifarley/docker-alpine-oraclejdk10:full.svg)](https://imagelayers.io/?images=elifarley/docker-alpine-oraclejdk10:full 'Get your own badge on imagelayers.io')


Consider using `develar/java` image (~120MB) if you only need JRE (you can run
java applications, but cannot build/compile them).


Usage Example
-------------

```bash
$ echo 'public class Main { public static void main(String[] args) { System.out.println("Hello World"); } }' > Main.java
$ docker run --rm -v "$(pwd)":/mnt --workdir /mnt elifarley/docker-alpine-oraclejdk10:slim sh -c "javac Main.java && java Main"
```

Once you have run this command you will get printed 'Hello World' from Java!
