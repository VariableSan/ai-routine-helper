FROM node:20.15.0-alpine

RUN npm install -g pnpm

WORKDIR /app

COPY package*.json pnpm-lock.yaml .env ./

RUN pnpm i

COPY . .

ENV VITE_APP_PORT ${VITE_APP_PORT}

RUN pnpm build-only

EXPOSE ${VITE_APP_PORT}

CMD [ "pnpm", "preview-only" ]