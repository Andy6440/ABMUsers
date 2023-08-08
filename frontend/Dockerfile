FROM node:18

# Set the working directory
WORKDIR /app

# Install the dependencies
COPY package*.json ./
RUN npm install

# Copy the rest of the application
COPY . /app
