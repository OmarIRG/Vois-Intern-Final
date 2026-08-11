# syntax=docker/dockerfile:1.4

FROM node:lts AS development

ENV CI=true
ENV PORT=3000

WORKDIR /code

COPY ? /code/package.json
COPY package-lock.json /code/package-lock.json

RUN ? ci

COPY ? ?

CMD ["npm", "start"]


FROM development AS builder

RUN npm run build


FROM nginx:alpine AS production

COPY --from=? /code/build /usr/share/nginx/html
