[![Build Status](https://travis-ci.org/xujintao/docker4cpp.svg?branch=master)](https://travis-ci.org/xujintao/docker4cpp)

docker environment for c++ development.

## Summary  
Repository name in Docker Hub: [xujintao/docker4cpp](https://hub.docker.com/r/xujintao/docker4cpp)  

## Image and tags  
* [xujintao/docker4cpp:ubuntu-dev](https://github.com/xujintao/docker4cpp/tree/master/ubuntu-dev)  
* [xujintao/docker4cpp:centos-dev](https://github.com/xujintao/docker4cpp/tree/master/centos-dev)  

Due to docker is not friendly with container environment variable, so we must enable it explicitly at the beginning of build.sh:
```sh
if [ -f /opt/rh/devtoolset-7/enable ];then
echo test /opt/rh/devtoolset-7/enable
source /opt/rh/devtoolset-7/enable
fi
```
## Understand
* The ubuntu-dev image is a ubuntu14.04 based cpp development environment which packed with gcc-7, g++-7, wget, make, 
libboost-log1.54-dev, libboost-system1.54-dev, libboost-thread1.54-dev and libboost-filesystem1.54-dev in 
and it is primary assigned to compiling https://github.com/xujintao/ratel.  

* Alternatively, centos-dev image owners the same features as ubuntu-dev except for that it is based on centos7.4.  

* Both of the two developing image will build ratel project field with travis-ci. The travis-ci 
[ymal](https://github.com/xujintao/ratel/blob/master/.travis.yml) on ratel shows how they work with each other.  

## License

[MIT](https://github.com/xujintao/docker4cpp/blob/master/LICENSE)