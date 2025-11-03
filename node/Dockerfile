# 1. Start with a lightweight Node.js base image
FROM node:18-alpine

# 2. Set the working directory inside the container
WORKDIR /app

# 3. Copy package.json and package-lock.json
# This is done first to take advantage of Docker's layer caching.
# 'npm install' will only re-run if these files change.
COPY package*.json ./

# 4. Install the application dependencies
RUN npm install

# 5. Copy the rest of your application's code
COPY . .

# 6. Expose the port your app runs on (e.g., 3000)
EXPOSE 3000

# 7. Define the command to run your app
CMD [ "node", "index.js" ]