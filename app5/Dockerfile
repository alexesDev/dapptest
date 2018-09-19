FROM node:10.8-alpine as build

WORKDIR /app
COPY package.json yarn.lock /app/
RUN yarn

COPY . /app/
RUN yarn build

FROM nginx:1.15.2-alpine
COPY --from=build /app/build /usr/share/nginx/html
