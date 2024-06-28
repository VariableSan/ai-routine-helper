FROM node:20.15.0-alpine AS builder

RUN npm install -g pnpm

WORKDIR /app

COPY package*.json pnpm-lock.yaml ./

RUN pnpm i

COPY . .

RUN pnpm build

FROM node:20.15.0-alpine

WORKDIR /app

COPY --from=builder /app/dist ./dist
COPY --from=builder /app/node_modules ./node_modules

EXPOSE 3000

CMD [ "node", "dist/main"]
