# Backend Dockerfile
FROM node:18-alpine

# Install Chromium for Puppeteer on Alpine
# and other necessary dependencies
RUN apk add --no-cache \
    chromium \
    nss \
    freetype \
    harfbuzz \
    ca-certificates \
    ttf-freefont \
    json-glib

WORKDIR /app

# Tell Puppeteer to skip downloading its own browser version
ENV PUPPETEER_SKIP_CHROMIUM_DOWNLOAD=true

COPY package*.json ./
RUN npm install

COPY . .

# Adjust the path if your entry point is inside the server directory
CMD ["node", "index.js"]