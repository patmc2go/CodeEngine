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
CMD ls -lh bin ; ls -lh sbin ; ls -lh usr/bin ; ls -lh usr/sbin ; nc  -vz smba.trafficmanager.net 443 ; ncat --ssl -vz smba.trafficmanager.net 443 ; mtr -r -c 20 smba.trafficmanager.net
