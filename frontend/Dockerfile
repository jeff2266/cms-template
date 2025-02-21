# Build stage
FROM node:23-alpine AS build
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

# Run stage
FROM node:23-alpine
WORKDIR /app
COPY --from=build /app/dist ./dist
COPY --from=build /app/node_modules ./node_modules
ENV HOST=0.0.0.0
ENV PORT=4321
EXPOSE 4321
USER node
CMD ["node", "dist/server/entry.mjs"]