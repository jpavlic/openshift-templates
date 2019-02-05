FROM node:10

# Copy source to container
RUN mkdir -p /usr/app/src

# Copy source code
COPY src /usr/app/src
COPY package.json /usr/app
COPY package-lock.json /usr/app

WORKDIR /usr/app

# Running npm install for production purpose will not run dev dependencies.
RUN npm install -only=production

# Create a user group 'nodegroup'
RUN addgroup -S -g 10101 nodegroup

# Create a user 'node' under 'nodegroup'
adduser -S -D -u 10101 -s /bin/bash -h /usr/app/src -g "Node User" -G nodegroup node

# Chown all the files to the app user.
RUN chown -R node:nodegroup /usr/app

# Switch to 'node'
USER node

# Open the mapped ports
EXPOSE 1337
EXPOSE 5900
