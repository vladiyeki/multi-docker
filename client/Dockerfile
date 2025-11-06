FROM node:16-alpine as builder
WORKDIR '/app'
COPY ./package.json ./
RUN npm install
COPY . .
RUN npm run build

FROM nginx
EXPOSE 3000
COPY ./ngninx/default.conf /etc/ngninx/conf.d/default.conf
COPY --from=builder /app/build /ust/share/ngninx/html

