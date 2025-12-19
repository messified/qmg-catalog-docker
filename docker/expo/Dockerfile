FROM node:20-alpine
WORKDIR /app
COPY package.json package-lock.json ./
RUN npm install
COPY . .
WORKDIR /app/apps/expo
RUN npm install -g expo-cli
EXPOSE 8081 19000 19001 19002
