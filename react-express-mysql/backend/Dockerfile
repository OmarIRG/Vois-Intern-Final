# syntax=docker/dockerfile:1.4

FROM node:lts AS development

ARG NODE_ENV=production
ENV NODE_ENV=$NODE_ENV

WORKDIR ?

ARG PORT=80
ENV PORT=$PORT

EXPOSE $PORT 9229 9230

COPY ? /code/package.json
COPY ? /code/package-lock.json

RUN ? ?

HEALTHCHECK --interval=30s \
  CMD node healthcheck.js

COPY ? ?

CMD ["node", "src/index.js"]
