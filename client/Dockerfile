FROM node:14.15.1

WORKDIR /vue-app

COPY package.json .
COPY yarn.lock .

RUN yarn install

COPY . .

CMD ["yarn", "dev"]
