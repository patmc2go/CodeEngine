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
apache2-utils \
nginx

COPY --from=0 /helloworld /helloworld
#CMD echo "=== ls bin" ; ls -lh bin ; echo "=== ls sbin" ;  ls -lh sbin ; echo "=== ls usr/bin" ;  ls -lh usr/bin ; echo "=== ls usr/sbin" ;  ls -lh usr/sbin ; echo "========= qrs-marker"; echo "Checking network IP/connect for host: smba.trafficmanager.net"; x=1; y=500; while [ $x -le $y ]; do echo; echo "===" ; echo "check cycle $x of $y"; echo "--- smba"; dig +short smba.trafficmanager.net; echo "===" ; openssl s_client -servername smba.trafficmanager.net -connect smba.trafficmanager.net:443 -showcerts < /dev/null 2>/dev/null | openssl x509 -text -noout | grep 'DNS' ; nc -vz smba.trafficmanager.net 443 ; echo "--- whitepages"; dig +short wp-search-gateway-api-key-5t8mxuav.uc.gateway.dev; echo "===" ; openssl s_client -servername wp-search-gateway-api-key-5t8mxuav.uc.gateway.dev -connect wp-search-gateway-api-key-5t8mxuav.uc.gateway.dev:443 -showcerts < /dev/null 2>/dev/null | openssl x509 -text -noout | grep 'DNS' ; nc -vz wp-search-gateway-api-key-5t8mxuav.uc.gateway.dev 443 ;  sleep 1; ((x++)); done; echo "--- curl targettester/headers";  curl -s https://targettester.mybluemix.net/headers ; echo "--- ab targettester/headers"; ab -n 10 -c 1 https://targettester.mybluemix.net/headers ;
