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

RUN groupadd -r nodeuser
RUN useradd -r -g nodeuser nodeuser

# Chown all the files to the app user.
RUN chown -R nodeuser:nodeuser /usr/app

# Switch to 'node'
USER nodeuser

# Open the mapped ports
EXPOSE 1337
EXPOSE 5900
