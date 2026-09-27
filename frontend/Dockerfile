FROM node:23-alpine

WORKDIR /app

COPY package*.json ./

# Install dependencies
RUN npm install --force

RUN npm_config_legacy_peer_deps=true npx update-browserslist-db@latest

# Add this line before running your npm installs or updates
RUN npm config set legacy-peer-deps true

# Your existing command will now work perfectly
RUN npx update-browserslist-db@latest


COPY . .

# Expose port 3000
EXPOSE 3000

# Start the application
CMD ["npm", "run", "start"]
