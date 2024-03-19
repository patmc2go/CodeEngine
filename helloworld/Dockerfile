FROM golang:alpine
COPY helloworld.go /

RUN go build -o /helloworld /helloworld.go

# Copy the exe into a smaller base image
#FROM alpine
FROM node:14

# Install debug tools
RUN apt-get update && apt-get -y install mtr \
nmap \
netcat \
dnsutils \
traceroute \
apache2-utils \
nginx

COPY --from=0 /helloworld /helloworld
CMD pwd; ls -lha /etc/nginx/; echo; echo "cat nginx.conf"; echo; cat /etc/nginx/nginx.conf; echo; echo "which nginx"; echo; which nginx; ls -lh /etc/nginx/modules-enabled/; /helloworld
