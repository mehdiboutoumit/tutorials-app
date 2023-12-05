FROM node:16-alpine as build
WORKDIR /app
COPY . .
RUN npm install
RUN npm run build --prod

# Stage 2: Use Nginx to serve the build
FROM nginx:1.25.3-alpine
RUN apk --no-cache upgrade --available openssl libx11

# Add labels for metadata
LABEL maintainer="BOUTOUMIT EL MEHDI" \
      version="1.0"

# Expose port and specify the version of Nginx
EXPOSE 80

# Copy the built Angular app to the Nginx web server directory
COPY --from=build /app/dist/angular-16-crud /usr/share/nginx/html

# Set a non-root user for security
USER nginx