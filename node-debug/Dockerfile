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

RUN groupadd -g 999 nodeuser && \
    useradd -r -u 999 -h /usr/app/src -g nodegroup nodeuser
USER nodeuser

# Chown all the files to the app user.
RUN chown -R node:nodegroup /usr/app

# Switch to 'node'
USER node

# Open the mapped ports
EXPOSE 1337
EXPOSE 5900
