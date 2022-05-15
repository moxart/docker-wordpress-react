FROM node:16.14.2 as build
WORKDIR /app
ENV PATH /app/node_modules/.bin:$PATH
COPY ./my-react-app/package.json .
COPY ./my-react-app/package-lock.json .
COPY ./my-react-app/ .
RUN npm install
CMD [ "npm", "run", "build" ]

FROM nginx:alpine
COPY --from=build /app/build /usr/share/nginx/html
RUN rm -rf /etc/nginx/conf.d/default.conf
RUN rm -rf /etc/nginx/conf.d
RUN mkdir /etc/nginx/conf.d
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
EXPOSE 80
CMD [ "nginx", "-g", "daemon off;" ]
