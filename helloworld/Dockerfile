#FROM golang:alpine
FROM node:14
#COPY helloworld.go /
#RUN go build -o /helloworld /helloworld.go

# Copy the exe into a smaller base image
#FROM alpine-bash

# Install debug tools
RUN apt-get update && apt-get -y install mtr \
nmap \
netcat \
dnsutils \
traceroute \
apache2-utils 

#COPY --from=0 /helloworld /helloworld
CMD echo "=== ls bin" ; ls -lh bin ; echo "=== ls sbin" ;  ls -lh sbin ; echo "=== ls usr/bin" ;  ls -lh usr/bin ; echo "=== ls usr/sbin" ;  ls -lh usr/sbin ; nc  -vz smba.trafficmanager.net 443 ; ncat --ssl -vz smba.trafficmanager.net 443 ; mtr -r -c 20 smba.trafficmanager.net
