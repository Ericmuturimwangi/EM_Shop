# Use the official Node.js image as a parent image
FROM node:18-slim

# Set the working directory in the container
WORKDIR /app

# Copy the package.json and package-lock.json (or yarn.lock) first for caching dependencies
COPY package.json package-lock.json* ./

# Install dependencies
RUN npm install

# Copy the rest of the application
COPY . .

# Build the Vue.js app
RUN npm run build

# Expose the port the app runs on
EXPOSE 8080

# Serve the app with a static file server (e.g., nginx)
CMD ["npm", "run", "serve"]