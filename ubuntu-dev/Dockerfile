FROM ubuntu:14.04
MAINTAINER xujintao <xujintao@126.com>

# repare dev environment
RUN apt-get -y update && \
    apt-get -y install software-properties-common && \
    apt-add-repository -y "ppa:ubuntu-toolchain-r/test" && \
    apt-get -y update && \
    apt-get -y install gcc-7 g++-7 libboost-all-dev make && \
    apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/temp/* && \
    ln -s /usr/bin/gcc-7 /usr/bin/gcc -f && \
    ln -s /usr/bin/g++-7 /usr/bin/g++ -f

WORKDIR "/project"
ENTRYPOINT exec ./build.sh