FROM node:18

WORKDIR /app

COPY package.json package-lock.json ./

# Install chokidar@3 explicitly (fix for missing dependency)
RUN npm install chokidar@3 --legacy-peer-deps

# Your existing postcss fix
RUN npm install postcss@8.4.21 postcss-safe-parser@6.0.0 --legacy-peer-deps

# Install rest of the dependencies
RUN npm install --legacy-peer-deps

COPY . .

EXPOSE 3000

ENV NODE_OPTIONS=--openssl-legacy-provider
ENV PORT=3000

CMD ["npm", "start"]