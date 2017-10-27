# centos-docker

[![](https://dockerbuildbadges.quelltext.eu/status.svg?organization=ssgreg&repository=centos-docker)](https://hub.docker.com/r/ssgreg/centos-docker/builds/)

Docker in Docker

## Supported tags

* `latest`
* `7.4.1708-17.05.0.ce`


## What is Docker in Docker?

The images allows you to run Docker from your CI system, while this CI system itself is in a container. Your be able to build, run and push containers and images. All you need is to expose the Docker socket to your CI container:

```
docker run ... -v /var/run/docker.sock:/var/run/docker.sock ssgreg/centos-docker ...
```

Now your container controls Docker engine that is hosting the container, so it can start sibling containers. It almost like Docker in Docker but it has no nesting side affects and other real Docker in Docker issues.


## Installation & Usage

Pull the images:

```
# docker pull ssgreg/centos-docker:latest
```

Run a container from the image:

```
# docker run --rm -it -v /var/run/docker.sock:/var/run/docker.sock ssgreg/centos-docker
```

Use the Docker:

```
[root@9e5035eed961 /]# docker images
REPOSITORY                                          TAG                 IMAGE ID            CREATED             SIZE
ssgreg/centos-docker                                latest              58edbffc7cbd        5 minutes ago       392MB
```

