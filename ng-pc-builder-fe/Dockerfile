# Stage 1: Build the Angular application
FROM node:16 as build

WORKDIR /app
COPY package.json package-lock.json ./

RUN npm install
COPY . .
RUN npm run build

# Stage 2: Serve the application with nginx
FROM nginx:1.21.1

COPY --from=build /app/dist/* /usr/share/nginx/html/
