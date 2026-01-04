# Stage 1: Build
FROM node:18-alpine AS build
WORKDIR /app

COPY app/package*.json ./
RUN npm install --only=production

COPY app/ .

# Stage 2: Runtime
FROM node:18-alpine
WORKDIR /app

COPY --from=build /app .

EXPOSE 3000
CMD ["node", "index.js"]

