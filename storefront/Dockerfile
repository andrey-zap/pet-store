FROM node:8.15.1-alpine AS build-stage
COPY . /app
WORKDIR /app
RUN npm install --production
RUN npm run build

FROM nginx:alpine 
COPY --from=build-stage /app/dist/ /var/www/