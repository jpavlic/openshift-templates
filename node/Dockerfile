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

RUN groupadd -r nodegroup
RUN useradd -r -g nodegroup node

USER nodeuser

# Chown all the files to the app user.
RUN chown -R node:nodegroup /usr/app

# Switch to 'node'
USER node

# Open the mapped ports
EXPOSE 1337
EXPOSE 5900
