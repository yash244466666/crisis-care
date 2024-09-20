# Use Node.js base image
FROM node:18

# Create app directory inside the container
WORKDIR /app

# Copy package.json and package-lock.json for dependency installation
COPY package.json package-lock.json /app/

# Install dependencies
RUN npm install

# Copy the rest of the app's source code
COPY . /app

# Expose the port used by the app
EXPOSE 3001

# Generate Prisma Client before starting the backend
RUN npx prisma generate

# Start the backend service
CMD ["npm", "run", "start:dev"]

# Run prisma migrate deploy to apply the migrations
# RUN npx prisma migrate deploy --name init
