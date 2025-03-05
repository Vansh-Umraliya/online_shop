# Base Image Where only pakages install of npm 

FROM node:18 AS builder

WORKDIR /app

COPY package*.json ./

RUN npm install 

COPY . .

# base image slim image only application 

FROM node:18-alpine

WORKDIR /app

COPY --from=builder /app .

EXPOSE 5173 

CMD ["npm","run","dev"]
