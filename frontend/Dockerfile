# Use the official Node.js image as the base image
FROM node:18

# Set the working directory
WORKDIR /usr/src/app

# Copy the package.json and package-lock.json files
COPY package*.json ./

# Install the dependencies
RUN npm install

# Copy the rest of the application
COPY . .

# Build the application
RUN npm run build

# Use the Nginx image to serve the built application
FROM nginx:alpine

# Copy the built application from the previous stage
COPY --from=0 /usr/src/app/dist /usr/share/nginx/html

# Expose port 81
EXPOSE 81

# Start Nginx
CMD ["nginx", "-g", "daemon off;"]
