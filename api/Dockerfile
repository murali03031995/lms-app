# base image as node-20
FROM node:20

# Create app directory and cd to app directory
WORKDIR /app

# copy code from host server to container into app folder
COPY . .

# installs node module - dependencies for app
RUN npm install

# Make the database ready
RUN npx prisma generate

# builds the application
RUN npm run build

# Expose port 3000 on container level
EXPOSE 3000

# Start app
CMD [ "npm", "start" ]
