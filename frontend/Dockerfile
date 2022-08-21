FROM node:16-alpine as builder
WORKDIR '/app'
COPY package.json .
RUN npm install
COPY . .
RUN npm run build

FROM nginx # https://www.udemy.com/course/docker-and-kubernetes-the-complete-guide/learn/lecture/29412010#overview
COPY --from=builder /app/build /usr/share/ngin/html