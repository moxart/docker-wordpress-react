FROM node:16.14.2
WORKDIR /app
ENV PATH /app/node_modules/.bin:$PATH
COPY ./my-react-app/package.json .
COPY ./my-react-app/package-lock.json .
COPY ./my-react-app/ .
RUN npm install
EXPOSE 3000
CMD [ "npm", "start" ]
