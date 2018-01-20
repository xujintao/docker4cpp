FROM centos:7.4.1708
MAINTAINER xujintao <xujintao@126.com>

# repare dev environment
RUN yum install -y centos-release-scl && \
#    yum install -y yum-utils && \
#    yum-config-manager --enable rhel-server-rhscl-7-rpms && \
    yum install -y devtoolset-7-gcc devtoolset-7-gcc-c++ devtoolset-7-gdb && \
    source /opt/rh/devtoolset-7/enable && \
    yum install -y wget && \
    wget https://sourceforge.net/projects/boost/files/boost/1.54.0/boost_1_54_0.tar.gz/download && \
    tar -xzvf boost_1_54_0.tar.gz && cd boost_1_54_0 && \
    ./booststrap.sh && ./b2 && \
    yum clean all -y

#ADD ./boost_1_54_0/boost /usr/include
#ADD ./boost_1_54_0/stage/lib /usr/lib64

WORKDIR "/project"
ENTRYPOINT exec ./build.sh