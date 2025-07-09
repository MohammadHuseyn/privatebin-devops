FROM alpine:3.19

RUN apk add --no-cache php php-fpm php-opcache php-gd php-mbstring php-zip nginx git unzip curl

WORKDIR /var/www

RUN curl -sSL https://github.com/PrivateBin/PrivateBin/archive/refs/tags/1.5.1.zip -o pb.zip && \
    unzip pb.zip && mv PrivateBin-* privatebin && rm pb.zip

COPY nginx.conf /etc/nginx/nginx.conf

WORKDIR /var/www/privatebin

CMD php-fpm -D && nginx -g 'daemon off;'
