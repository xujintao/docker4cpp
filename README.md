docker environment for c++ development and runtime.

## Summary  
Repository name in Docker Hub: [xujintao/docker4cpp](https://hub.docker.com/r/xujintao/docker4cpp)  

## Image and tags  
* [xujintao/docker4cpp:ubuntu-dev](https://github.com/xujintao/docker4cpp/tree/master/ubuntu-dev)  
* [xujintao/docker4cpp:ubuntu-runtime](https://github.com/xujintao/docker4cpp/tree/master/ubuntu-runtime)  
* [xujintao/docker4cpp:centos-dev](https://github.com/xujintao/docker4cpp/tree/master/centos-dev)  

## Understand
* xujintao/docker4cpp:ubuntu-dev image is a cpp development environment which packed with 
gcc-7, g++-7 and libboost1.54.0-dev-all in and it is primary assigned to compiling https://github.com/xujintao/ratel.  

* However, xujintao/docker4cpp:ubuntu-runtime as a cpp runtime environment image, here auto 
built with dockerhub is a test image, and the really runtime image(see https://github.com/xujintao/ratel/blob/master/Dockerfile) 
will be built field with travis-ci.  

* xujintao/docker4cpp:centos-dev is prepared for the building job with travis-ci which based on ubuntu14.04 trusty.  

* The travis-ci ymal on ratel(https://github.com/xujintao/ratel/blob/master/.travis.yml) shows how they work with each other.  

## License

[MIT](https://github.com/xujintao/docker4cpp/blob/master/LICENSE)