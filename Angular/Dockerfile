
FROM node:16-alpine as build

WORKDIR /app
COPY package*.json ./
RUN npm install

COPY . .
RUN npm run build --prod

FROM nginx:1.17.1-alpine

COPY --from=build /app/dist/crudtuto-Front /usr/share/nginx/html
