# Use the official Node.js 18 image based on Alpine Linux
FROM node:18-alpine

# Set the working directory
WORKDIR /app

# Copy package.json and package-lock.json to leverage Docker cache
COPY package*.json ./

# Install dependencies
RUN npm install --production

# Copy the rest of the application code
COPY . .

ENV REACT_APP_PUBLIC_FOLDER = http://localhost:5000/images/

# Expose port 3000
EXPOSE 3000

# Start the application
CMD ["npm", "start"]
