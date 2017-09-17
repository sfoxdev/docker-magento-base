# Magento2

Magento 2.1.9 container based on Ubuntu 16.04 + Apache 2.4 + PHP 7.0.22 and installed with Composer

[![Docker Build Status](https://img.shields.io/docker/build/sfoxdev/magento-base.svg?style=flat-square)]()
[![Docker Build Status](https://img.shields.io/docker/automated/sfoxdev/magento-base.svg?style=flat-square)]()
[![Docker Build Status](https://img.shields.io/docker/pulls/sfoxdev/magento-base.svg?style=flat-square)]()
[![Docker Build Status](https://img.shields.io/docker/stars/sfoxdev/magento-base.svg?style=flat-square)]()

## Usage

### Build and run with docker-compose
```
docker-compose up -d --build
```
### OR

### Build and run container with docker

```
docker build -t sfoxdev/magento-base .
```
and
```
docker run -d --env-file=magento.env -v ./data:/root/magento-data -p 80:80 --name magento-base sfoxdev/magento-base
```

### Get complete dump of Magento2 store from container volume to your folder

```
cp $(docker inspect -f '{{(index .Mounts 0).Source }}' magento-base)/* .
```
