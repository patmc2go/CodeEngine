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

# Copy custom nginx.conf to live system
#COPY nginx.conf /etc/nginx/

COPY --from=0 /helloworld /helloworld
CMD pwd; ls -lha /etc/nginx/; echo; echo "cat nginx.conf"; echo; echo "==="; cat /etc/nginx/nginx.conf; echo; echo "which nginx"; echo; which nginx; echo; echo "look at /etc/nginx/modules-enabled"; echo; echo "==="; ls -lh /etc/nginx/modules-enabled/; echo; echo "look at /etc/nginx/conf.d/"; echo; echo "==="; ls -lh /etc/nginx/conf.d/; echo; echo "look at /etc/nginx/sites-enabled"; echo; echo "==="; ls -lh /etc/nginx/sites-enabled; echo; echo "look at default"; echo; echo "==="; cat /etc/nginx/sites-enabled/default; ps aux; nginx;
