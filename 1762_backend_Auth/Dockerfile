# Use an official Node runtime as a parent image
FROM node:14

# Set the working directory to /1762_backend_auth
WORKDIR /1762_backend_auth

# Copy the package.json and package-lock.json to the working directory
COPY package*.json ./

# Install the dependencies
RUN npm install

# Copy the rest of the application code to the working directory
COPY . .

# Expose the backend port
EXPOSE 1762

# Start the backend server
CMD ["npm", "start"]
