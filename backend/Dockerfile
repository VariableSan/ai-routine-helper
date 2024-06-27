FROM node:20.15.0-alpine

RUN npm install -g pnpm

WORKDIR /app

COPY package*.json pnpm-lock.yaml .env ./

RUN pnpm i

COPY . .

ENV APP_PORT ${APP_PORT}

RUN pnpm build

EXPOSE ${APP_PORT}

CMD [ "pnpm", "start:prod" ]
