FROM node:lts-alpine as build-stage
WORKDIR /proyectfinalvue3

COPY package*.json /proyectfinalvue3
RUN npm install -g @vue/cli
RUN npm install -g json-server
RUN npm install

COPY . /proyectfinalvue3

RUN npm run build --prod

CMD ["npm","run", "serve"]

FROM nginx:stable-alpine as production-stage
COPY --from=build-stage /proyectfinalvue3/dist /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]