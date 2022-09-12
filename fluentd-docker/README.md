# fluentd-docker

Ref. https://docs.fluentd.org/container-deployment/install-by-docker


## How to run

### Step 1: Install Docker and checkout this directory
```
$ # To install Docker, refer https://docs.docker.com/desktop/install/mac-install/
$ git clone https://github.com/allenhwkim/hello-docker.git
$ cd hello-docker/fluentd-docker
```

### Step 2: Download fluentd docker image from Docker hub to local
```
$ docker pull fluent/fluentd:edge-debian
$ docker images
REPOSITORY       TAG           IMAGE ID       CREATED          SIZE
hello-docker     latest        65aafe5ee675   20 minutes ago   864MB
fluent/fluentd   edge-debian   3b1d0183577b   2 weeks ago      250MB
```

### Step 3: Run docker images with your own fluentd configuration
```
$ cp cp fluentd.conf $(pwd)/tmp/fluentd.conf
$ docker run -p 9880:9880 -v $(pwd)/tmp:/fluentd/etc fluent/fluentd:edge-debian -c /fluentd/etc/fluentd.conf
```

