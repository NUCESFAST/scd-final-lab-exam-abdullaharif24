# 1762: Use an official Node runtime as a parent image
FROM node:14

# 1762: Set the working directory to /1762_frontend
WORKDIR /1762_frontend_client

# 1762: Copy the package.json and package-lock.json to the working directory
COPY package*.json ./

# 1762: Install the dependencies
RUN npm install

# 1762: Copy the rest of the application code to the working directory
COPY . .

# 1762: Build the React application for production
RUN npm run build

# 1762: Use an Nginx image to serve the static files
FROM nginx:alpine
COPY --from=0 /1762_frontend_client/build /usr/share/nginx/html

# 1762: Expose port 1762
EXPOSE 1762

# 1762: Start Nginx server
CMD ["nginx", "-g", "daemon off;"]
