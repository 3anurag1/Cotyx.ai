# Use a lightweight Node.js image based on Alpine Linux
FROM node:18-alpine

# Set the working directory inside the container
WORKDIR /app

# Copy package.json and package-lock.json to leverage caching
COPY package*.json ./

# Install npm dependencies
RUN npm install

# Copy your application's source code
COPY ./src /app/src

# The command to start the development server using nodemon,
# which watches for file changes and automatically restarts the server.
CMD ["npm", "run", "dev"]