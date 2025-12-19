FROM node:20-alpine
WORKDIR /app
COPY package.json package-lock.json ./
RUN npm install
COPY . .
WORKDIR /app/apps/web
EXPOSE 3000
