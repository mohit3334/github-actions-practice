FROM node:20-alpine

WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .
RUN npm run build


FROM nginx:stable-alpine

COPY --form=build /app/dist /usr/share/nginx/html

EXPOSE 80