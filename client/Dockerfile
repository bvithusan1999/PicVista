# Use an official node image as the base image
FROM node:14

# Set the working directory
WORKDIR /app

# Copy package.json and package-lock.json to the working directory
COPY package.json package-lock.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application code to the working directory
COPY . .

# Build the React application for production
RUN npm run build

# Install a simple HTTP server to serve the static files
RUN npm install -g serve

# Set the command to serve the build directory
CMD ["serve", "-s", "build"]

# Expose the port the app runs on
EXPOSE 3000
