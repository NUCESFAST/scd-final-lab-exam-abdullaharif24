# 1762: Use an official Node runtime as a parent image
FROM node:14

# 1762: Set the working directory to /1762_backend
WORKDIR /1762_backend

# 1762: Copy the package.json and package-lock.json to the working directory
COPY package*.json ./

# 1762: Install the dependencies
RUN npm install

# 1762: Copy the rest of the application code to the working directory
COPY . .

# 1762: Expose the backend port
EXPOSE 1762

# 1762: Start the backend server
CMD ["npm", "start"]
