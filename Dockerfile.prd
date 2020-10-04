# FROM node:alpine as builder   NOT WORKING FOR AWS BUILDERS
FROM node:alpine
WORKDIR /app
COPY ./package.json .
RUN npm i
COPY . .
RUN npm run build

FROM nginx
# COPY --from=builder /app/build /usr/share/nginx/html
COPY --from=0 /app/build /usr/share/nginx/html