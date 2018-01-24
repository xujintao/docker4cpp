FROM ubuntu:14.04
MAINTAINER xujintao <xujintao@126.com>

# prepare dev environment
RUN echo "===>update apt repository list" && apt-get -y update && \
    echo "===>install software-properties-common" && apt-get -y install software-properties-common && \
    echo "===>add ubuntu toolchain repository" && apt-add-repository -y "ppa:ubuntu-toolchain-r/test" && \
    echo "===>update apt source list again" && apt-get -y update && \
    echo "===>install toolchain " && apt-get -y install gcc-7 g++-7 make && \
#    echo "===>install boost" && apt-get -y install libboost-all-dev && \
    echo "===>install boost" && apt-get -y install libboost-log1.54-dev \
                                                   libboost-system1.54-dev \
                                                   libboost-thread1.54-dev \
                                                   libboost-filesystem1.54-dev && \
    echo "===>rm apt repository and tmp files" && apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/temp/* && \
    echo "===>create toolchain soft link" && ln -s /usr/bin/gcc-7 /usr/bin/gcc -f && ln -s /usr/bin/g++-7 /usr/bin/g++ -f

WORKDIR "/project"
CMD ./build.sh