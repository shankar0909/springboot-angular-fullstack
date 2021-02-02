#Stage 1
FROM node:latest as build-step
RUN mkdir  -p /app
WORKDIR /app
COPY package.json /app
RUN npm install
COPY . /app
RUN npm run build --prod

#Stage 2
FROM nginx:1.18.0-alpine
COPY --from=build-step /app/dist/angular-frontend /usr/share/nginx/html
EXPOSE 80
CMD ["nginx","-g","daemon off;"]
