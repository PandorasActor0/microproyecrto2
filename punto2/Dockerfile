FROM node:lts-alpine AS deploy

WORKDIR /deployment

COPY ["app/package.json", "app/package-lock.json", "./"]

RUN npm install

COPY app/ .

COPY --from=model-builder /app/model ./public/model

EXPOSE 3000

CMD ["node", "index.js"]