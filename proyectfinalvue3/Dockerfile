FROM node:lts-alpine
WORKDIR /proyectfinalvue3
COPY . .

RUN npm install --production="false"
RUN npm run build

EXPOSE 8086