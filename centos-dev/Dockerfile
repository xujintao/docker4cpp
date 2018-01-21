FROM centos:7.4.1708
MAINTAINER xujintao <xujintao@126.com>

# repare dev environment
RUN echo "===>install software collect" && yum install -y centos-release-scl && \
    echo "===>devtoolset-7" && yum install -y devtoolset-7-gcc devtoolset-7-gcc-c++ devtoolset-7-gdb && \
    echo "===>enable devtoolset-7" && source /opt/rh/devtoolset-7/enable && \
    echo "===>printf gcc version" && gcc --version && \
    echo "===>install wget" && yum install -y wget && \
    echo "===>printf pwd" && pwd && \
    echo "===>wget boost" && wget -q https://sourceforge.net/projects/boost/files/boost/1.54.0/boost_1_54_0.tar.gz/download && \
    echo "===>tar boost and cd" && tar -xzvf boost_1_54_0.tar.gz && cd boost_1_54_0 && \
    echo "===>build boost" && ./booststrap.sh && ./b2 && \
    echo "===>cp headers and libs" && cp -drf boost /usr/include && cp -drf stage/lib* /usr/lib64 && cd .. && \
    echo "===>yum clean all" && yum clean all -y && \
    echo "===>rm tmp files" && rm -rf boost*

#ADD ./boost_1_54_0/boost /usr/include
#ADD ./boost_1_54_0/stage/lib /usr/lib64

WORKDIR "/project"
ENTRYPOINT exec ./build.sh