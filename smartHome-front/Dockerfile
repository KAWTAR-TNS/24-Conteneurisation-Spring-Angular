# Dockerfile pour le frontend Smart House (Angular/React)
# Build multi-stage: Node.js + Nginx
#
# @author Hamza Aglagal
# @organization EMSI

# Stage 1: Build with Node.js
FROM node:14.15.0-alpine as builder
WORKDIR /app
COPY . .
RUN npm install
RUN npm run build

# Stage 2: Serve with Nginx
FROM nginx:alpine
COPY --from=builder /app/dist/smart-home /usr/share/nginx/html
