# Use official node image (tag 10-slim)
FROM node:10-slim
# Set the container application directory to /app
WORKDIR /app
# Execute npm install -g nodemon in the container
RUN npm install -g nodemon 
# Copy package*.json from the current folder to the current folder in the container
COPY package*.json /app
# Execute the following commands in the container :
RUN npm ci
RUN npm cache clean --force
RUN mv /app/node_modules /node_modules
# Copy the current folder (of the project) to the current folder in the container
COPY . /app
# Set the environment variable PORT to 80
ENV PORT 80
# Make port 80 available for links and/or publish
EXPOSE 80
# Define the command "nodemon server.js" to be run when launching the container
CMD nodemon server.js  