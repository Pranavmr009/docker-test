FROM node:14
# Create home directory and give a permission to node user
RUN mkdir -p /app && chown -R node:node /app

# Create app directory
WORKDIR /app

# Install dependencies
COPY package.json /app
# Using node user
USER node

RUN npm install

# Create a anonymous volume to exclude modules to be overwrite by bind mount 
VOLUME ["/app/node_modules"]

# Bundle app sources
COPY --chown=node:node . . 

EXPOSE 80

# environment variables for db credentials with default value
ENV MONGODB_USERNAME=root
ENV MONGODB_PASSWORD=secret

# Launch the app
CMD ["npm","start"]  