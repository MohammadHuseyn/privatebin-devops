FROM alpine:3.19

RUN apk add --no-cache php8 php8-fpm php8-opcache php8-gd php8-mbstring php8-zip nginx git unzip curl

WORKDIR /var/www

RUN curl -sSL https://github.com/PrivateBin/PrivateBin/archive/refs/tags/1.5.1.zip -o pb.zip && \
    unzip pb.zip && mv PrivateBin-* privatebin && rm pb.zip

COPY nginx.conf /etc/nginx/nginx.conf

WORKDIR /var/www/privatebin

CMD php-fpm8 -D && nginx -g 'daemon off;'
