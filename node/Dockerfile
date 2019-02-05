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

# Create a user group 'yodagroup'
RUN addgroup --system yodagroup

# Create a user 'yoda' under 'yodagroup'
RUN adduser --home /usr/app/src --shell /bin/bash yoda yodagroup

# Chown all the files to the app user.
RUN chown -R yoda:yodagroup /usr/app

# Switch to 'yoda'
USER yoda

# Open the mapped ports
EXPOSE 1337
EXPOSE 5900
