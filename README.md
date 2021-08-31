# docker-novnc

1. docker image: [dockerhub](https://hub.docker.com/r/wangz2019/docker-novnc)
2. source code: [github](https://github.com/ben-wangz/docker-novnc)
3. docs: [docker-novnc-docs](https://ben-wangz.github.io/docker-novnc)

## what's it

1. docker image of novnc client
2. mainly used for testing environment construction

## limitations

1. only supporting amd64 and arm64

## usage

1. requirements
    * system os and arch
        + linux & amd64 (tested with centos 8)
        + linux & arm64 (not tested, but it will be okay)
        + mac & amd64 (not tested, but it will be okay)
        + mac & arm64 (tested with mac mini whose chip is apple m1)
        + windows & x86_64 (not tested, but it will be okay)
    * jdk 8 or higher to run gradle scripts
    * docker to build/run service
2. start service
    * build docker image
        + optional
        + ```shell
          ./gradlew :buildDockerImage
          ```
    * run docker container
        + ```shell
          ./gradlew :runDockerContainer
          ```
        + ssh service will be exposed with port 1022
3. test service
    * TODO
4. stop service
    * ```shell
      ./gradlew :stopDockerContainer
      ```
5. you can also jump into the container with ssh
    * visit http://localhost:6080/
6. build multi-platform images and push them to docker registry
    * ```shell
      ./gradlew :pushDockerImage
      ```
    * you need an environment to build multi-platform
      images: [develop with docker](https://blog.geekcity.tech/#/docs/develop.with.docker)
