FROM node:6-alpine

EXPOSE 3000

RUN mkdir -p /usr/src/app
RUN apk add --no-cache tini

WORKDIR /usr/src/app

COPY package.json package.json

RUN npm install && npm cache clean --force

COPY . .

CMD [ "/sbin/tini", "--", "node", "./bin/www" ]
