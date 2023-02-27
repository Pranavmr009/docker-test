# Define an image dependency present in host machine or in dockerhub
FROM node

# Root folder where the commands must be executed (will be created in container if not exist)
WORKDIR /app

# Copy source files/folders to destination in the container
# optimize by copying package.json to store dependencies in cache before copying folder files
COPY package.json /app

# Run commands on images > Executed when the image is created
RUN npm install

# Copy new files/folders from source (in local machiine) to destination in the container
COPY . /app

# Informs docker that the container listens on the specified network ports at runtime 
# example docker run -p 4OOO:8081
EXPOSE 8081

# Run when the container is started base on the image
CMD ["node","server.js"]  