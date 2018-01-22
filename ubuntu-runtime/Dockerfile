FROM ubuntu:14.04
MAINTAINER xujintao <xujintao@126.com>

# prepare runtime
RUN apt-get -y update && \
#    apt-get -y install software-properties-common && \
#    apt-add-repository -y "ppa:ubuntu-toolchain-r/test" && \
#    apt-get -y update && \
#    apt-get -y install gcc-7 g++-7 libboost-all-dev make && \
    apt-get -y install libboost-log1.54.0 && \
    apt-get -y install libboost-system1.54.0 && \
    apt-get -y install libboost-thread1.54.0 && \
    apt-get -y install libboost-filesystem1.54.0 && \
    apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/temp/*

# host dir -> container dir
#ADD ./build/* /opt/www/ratel/

#CMD /opt/www/ratel/restart.sh