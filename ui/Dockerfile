FROM node:10 as build
WORKDIR /build
COPY . .
RUN NG_CLI_ANALYTICS=ci  npm install -g @angular/cli
RUN NG_CLI_ANALYTICS=ci npm install
RUN npm run build
EXPOSE 4200
FROM nginx
EXPOSE 80
WORKDIR /app
COPY --from=build /build/dist/poolmanger-ui .
COPY nginx.conf /etc/nginx/nginx.conf
