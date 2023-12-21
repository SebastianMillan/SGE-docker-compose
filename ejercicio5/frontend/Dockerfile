FROM node:10.13-alpine as angular
WORKDIR /home/app
RUN npm install -g @angular/cli@10
COPY . .
RUN npm ci
RUN ng build

FROM nginx:alpine
WORKDIR /usr/share/nginx/html
RUN rm index.html
COPY --from=angular /home/app/dist/frontend/ .
