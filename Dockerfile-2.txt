# Use the official Nginx image as the base image
FROM nginx:alpine

# Remove the default Nginx static assets
RUN rm -rf /usr/share/nginx/html/*

# Copy the static website files (HTML, CSS, etc.) to the Nginx directory
COPY . /usr/share/nginx/html

# Expose port 80
EXPOSE 80
EXPOSE 443

# Start Nginx server
CMD ["nginx", "-g", "daemon off;"]