# syntax=docker/dockerfile:1.4

FROM node:lts AS development

ARG NODE_ENV=production
ENV NODE_ENV=$NODE_ENV

WORKDIR /code

ARG PORT=80
ENV PORT=$PORT

EXPOSE $PORT 9229 9230

COPY package.json /code/package.json
COPY package-lock.json /code/package-lock.json
COPY .npmrc .
COPY .yarnrc.yml .

RUN npm ci

HEALTHCHECK --interval=30s \
  CMD node healthcheck.js

COPY . /code

CMD ["node", "src/index.js"]