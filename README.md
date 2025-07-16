# docker-freeradius
freeradius for docker and Lab

## Build the container
```
$ git clone https://github.com/fatman00/docker-freeradius.git
$ cd docker-freeradius
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
## Clean up all data
```
ubuntu:~$ docker system df   
TYPE            TOTAL     ACTIVE    SIZE      RECLAIMABLE
Images          2         1         243MB     243MB (99%)
Containers      1         1         1.608kB   0B (0%)
Local Volumes   0         0         0B        0B
Build Cache     0         0         0B        0B

docker image prune -a
```
