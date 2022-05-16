FROM nginx:1.21.6-alpine

RUN rm -rf /etc/nginx/nginx.conf
RUN rm -rf /etc/nginx/conf.d
RUN mkdir /etc/nginx/conf.d

COPY nginx.conf /etc/nginx/nginx.conf
COPY default.conf /etc/nginx/conf.d/default.conf

CMD [ "nginx", "-g", "daemon off;" ]
