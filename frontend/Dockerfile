# Use an official Node runtime as a parent image
FROM node:latest

# Set the working directory
WORKDIR /usr/src/app

# Install app dependencies
# A wildcard is used to ensure both package.json AND package-lock.json are copied
COPY package*.json ./

RUN npm install

# Bundle app source
COPY . .

# Build the TypeScript app
RUN npm run build

# Your app binds to port 3000, so use the EXPOSE instruction to have it mapped by the docker daemon
EXPOSE 3000

CMD ["node", "dist/app.js"]
