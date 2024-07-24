# Stage-1 build

# base image as node-20
FROM node:20 as build

# Create app directory
WORKDIR /app

# copy the code to container from host server
COPY . .

# installs dependencies
RUN npm install

# build the app - you will get dist folder
RUN npm run build

# Stage-2 deployment

# Docker file for nginx server to serve react app build files (spa routing)
FROM nginx

COPY --from=build /app/dist /usr/share/nginx/html

# Expose port 80 on container
EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
