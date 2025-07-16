# docker-freeradius
freeradius for docker and Lab

## Build the container
```
$ git clone https://github.com/fatman00/docker-freeradius.git .
$ docker build -t my-radius-image -f Dockerfile .
```
Start the container
```
docker run --rm -d --name my-radius -p 1812-1813:1812-1813/udp my-radius-image
```
Verify radius:
```
$ radtest bob test 127.0.0.1 0 testing123
```
## Stop the container if needed
```
docker stop my-radius
```
