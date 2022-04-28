# Install dependencies only when needed
FROM node:16-alpine AS node

RUN apk add --no-cache libc6-compat
WORKDIR /app
COPY ./pages ./pages
COPY ./components ./components
COPY package.json yarn.lock ./
RUN yarn install --frozen-lockfile

RUN yarn export

FROM nginx AS nginx_proxy

COPY --from=node /app/out /usr/share/nginx/html