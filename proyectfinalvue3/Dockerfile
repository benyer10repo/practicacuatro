FROM node:lts-alpine as build-stage

RUN npm install -g json-server
WORKDIR /proyectfinalvue3
COPY package*.json ./

RUN npm install

COPY . .

RUN npm run build

WORKDIR /proyectfinalvue3/database
ENTRYPOINT ["json-server", "db.json", "--port", "5000", "--host", "0.0.0.0"]

FROM nginx:stable-alpine as production-stage
COPY --from=build-stage /app/dist /usr/share/nginx/html
EXPOSE 8086
CMD ["nginx", "-g", "daemon off;"]