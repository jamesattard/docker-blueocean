# About

This project allows you to run Jenkins BlueOcean on a docker container and
accessing through http://jenkins.localhost/ by making use of
[nginx-proxy](https://hub.docker.com/r/jwilder/nginx-proxy/)

# Requirements

First make sure you have a local DNS Server that is able to proxy local requests
correctly. If you are using OSX or Linux, I suggest to use dnsmasq. The
following is the process to setup dnsmasq on OSX:

```sh
$ brew install dnsmasq
```

Update "/usr/local/etc/dnsmasq.conf" as follows:

```sh
listen-address=127.0.0.1
port=35353
address=/.localhost/127.0.0.1
```

Start dnsmasq as a service:

```sh
$ brew service start dnsmasq
```

Finally, create a new file, /etc/resolver/localhost, to resolve all .localhost
DNS requests:

```sh
port 35353
nameserver 127.0.0.1
```

# Installation

```sh
$ git clone https://github.com/jamesattard/docker-blueocean.git
$ cd docker-blueocean
$ docker-compose up
```

# Usage

Just point your browser to http://jenkins.localhost/
