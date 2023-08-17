FROM ubuntu:18.04

RUN apt-get update && apt-get install -y nginx
COPY ./example.html /var/www/html/

CMD ["nginx", "-g", "daemon off;"]