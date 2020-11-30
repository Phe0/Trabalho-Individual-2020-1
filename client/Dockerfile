FROM node:latest

RUN mkdir -p /vue-app
WORKDIR /vue-app

COPY package.json /vue-app
COPY yarn.lock /vue-app

RUN yarn

COPY . /vue-app

CMD ["yarn", "dev"]
