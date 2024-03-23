FROM mhart/alpine-node:12 AS DEVELOPMENT

# Define app directory
WORKDIR /app

# Install app dependencies
# A wildcard is used to ensure both package.json are copied
# Where available (npm@5+)
COPY package*.json ./

RUN npm Install

$ Copy app form source (current directory) to the the destination directory (container)
COPY . .

EXPOSE 8080

CMD ["node", "server.js"]

FROM mhart/alpine-node:12 AS TEST
WORKDIR /app
COPY --from=development /app/ .
RUN [npm", "run", "test"]

FROM mhart/alpine-node:12 AS PRODUCTION

# Create app directory
WORKDIR /app
COPYpackage*.json ./
RUN npm ci --only=production
# If you are building your code for production
]# RUN npm ci --only=production

# Copy app from current directory into the container
COPY . .

EXPOSE 8080

CMD ["node", "server.js"]
