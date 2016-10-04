# coldrye-debian-bind

[![coldrye/debian-bind](http://dockeri.co/image/coldrye/debian-bind)](https://hub.docker.com/r/coldrye/debian-bind/)


## Description

This packages bind in various releases based on coldrye/debian-tini.


## Image Releases

Images are released for the following debian releases.

- jessie
- testing

See https://hub.docker.com/r/coldrye/debian-bind/tags/ for a complete list.


## Environment

- PORT=<UdpPort> (default 53)
- CPUS=<NumCpus> (default 1)
- PROTO=<4|6> (default 4)


## Command

The command is set to ```/usr/sbin/named -g -p $PORT -$PROTO -n $CPUS```.


## Usage

General Usage

```
docker create -v $(pwd)/data:/etc/bind --net=host --name dns coldrye/debian-bind:<TAG>
```

