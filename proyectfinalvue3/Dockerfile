FROM node:lts-alpine
RUN npm install -g http-server
WORKDIR /proyectfinalvue3
COPY package*.json /proyectfinalvue3/

RUN npm install --production="false"

COPY ./proyectfinalvue3/

RUN npm run build

EXPOSE 8086
CMD [ "http-server", "dist" ]