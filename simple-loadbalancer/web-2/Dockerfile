FROM nginx
RUN mkdir /web
WORKDIR /web
COPY ./dist .
COPY ./nginx.conf /etc/nginx/nginx.conf