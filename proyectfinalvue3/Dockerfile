FROM node:lts-alpine as build-stage
RUN npm install -g http-server
WORKDIR /proyectfinalvue3
COPY package*.json /proyectfinalvue3/

RUN npm install --production="false"

COPY . .

RUN npm run build

EXPOSE 8086
CMD [ "http-server", "dist" ]