
FROM node:20-alpine as build
WORKDIR /app

COPY package*.json ./

RUN npm install -g @angular/cli

RUN npm install

COPY . .
# building the app
RUN npm run build

FROM nginx:1.25.3-alpine as production

COPY --from=build /app/dist/angular-16-crud/ /usr/share/nginx/html
# specifying the port 
EXPOSE 80

