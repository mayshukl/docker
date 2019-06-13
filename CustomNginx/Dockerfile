# This file will create an image of nginx with  debian:stretch-slim

FROM debian:stretch-slim

RUN apt-get update -y 

RUN apt-get install -y nginx 

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]  