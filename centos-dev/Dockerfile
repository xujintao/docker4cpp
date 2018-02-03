FROM centos:7.4.1708
MAINTAINER xujintao <xujintao@126.com>

# prepare dev environment
RUN echo "===>install software collections" && yum install -y centos-release-scl-rh && \
    echo "===>install devtoolset-7" && yum install -y devtoolset-7-gcc devtoolset-7-gcc-c++ devtoolset-7-gdb && \
    echo "===>enable devtoolset-7" && source /opt/rh/devtoolset-7/enable && \
#    echo "===>enable devtoolset-7 persistence" && echo "source /opt/rh/devtoolset-7/enable" >> ~/.bashrc && \
    echo "===>printf gcc version" && gcc --version && \
    echo "===>install make" && yum install -y make && \
    echo "===>install wget" && yum install -y wget && \
    
    # install boost
    echo "===>wget boost" && wget -q https://sourceforge.net/projects/boost/files/boost/1.54.0/boost_1_54_0.tar.gz && \
    echo "===>print pwd" && pwd && \
    echo "===>ls -al" && ls -al && \
    echo "===>tar boost and cd" && tar -xzf boost_1_54_0.tar.gz && cd boost_1_54_0 && \
    echo "===>build boost" && ./bootstrap.sh && ./b2 -d0 --with-log --with-thread --with-system --with-filesystem && \
    echo "===>cp headers and libs" && cp -drf boost /usr/include && cp -drf stage/lib/* /usr/lib64 && cd .. && \
    
    # install mysql-connector-c++
    echo "===>wget mysql-connector-c++-1.1.9" && wget -q \
                https://dev.mysql.com/get/Downloads/Connector-C++/mysql-connector-c++-1.1.9-linux-el7-x86-64bit.tar.gz && \
    echo "===>print pwd" && pwd && \
    echo "===>ls -al" && ls -al && \
    echo "===>tar connector and cd" && tar -xzf mysql-connector-c++-1.1.9-linux-el7-x86-64bit.tar.gz && \
    echo "===>cp libs" && cp -drf mysql-connector-c++-1.1.9-linux-el7-x86-64bit/lib/* /usr/lib64 && \
    
    # clean
    echo "===>yum clean all" && yum clean all -y && \
    echo "===>rm tmp files" && cd .. && rm -rf boost*

WORKDIR "/project"
CMD ./build.sh