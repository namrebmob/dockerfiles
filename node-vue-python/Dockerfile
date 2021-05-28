FROM python:alpine

ARG PORT
ENV PORT=${PORT:-8080}

EXPOSE ${PORT}

ARG NODE_ENV
ENV NODE_ENV=${NODE_ENV:-production}

RUN apk add --no-cache --update npm
RUN npm add --global @vue/cli

WORKDIR /src
