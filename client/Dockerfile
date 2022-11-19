FROM node:16-alpine as builder
WORKDIR '/app'
copy ./package.json ./
run npm install
copy . .
run npm run build

from nginx
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf 
copy --from=builder /app/build /usr/share/nginx/html