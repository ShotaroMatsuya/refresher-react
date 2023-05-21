FROM node:16-alpine

RUN apk update && \
  apk upgrade && \
  apk add --no-cache git zip

RUN npm install -g npm@9 

USER node

WORKDIR '/app'

COPY package*.json .

RUN npm ci

COPY --chown=node:node ./ ./

EXPOSE 3000

CMD [ "npm","run","start" ]