FROM alpine:3.18

# Install Nginx
RUN apk update && \
    apk upgrade && \
    apk add --no-cache nginx

# Set up the working directory
WORKDIR /usr/share/nginx/html

# Copy package.json and package-lock.json
COPY requirements/bonus/website/conf/new_portfolio-master/package.json .
COPY requirements/bonus/website/conf/new_portfolio-master/package-lock.json .

# Install npm dependencies
RUN apk add --no-cache nodejs npm 

# Copy nginx configuration
COPY requirements/bonus/website/conf/default.conf /etc/nginx/http.d/default.conf

# Copy the rest of the files
COPY requirements/bonus/website/conf/new_portfolio-master/dist /usr/share/nginx/html


# Expose port 80
EXPOSE 80

# Start nginx in the foreground
CMD ["nginx", "-g", "daemon off;"]




# FROM alpine:3.18
# RUN	apk update && \
# 	apk upgrade && \
# 	apk add --no-cache nginx

# COPY requirements/bonus/website/conf/default.conf /etc/nginx/http.d/default.conf

# COPY requirements/bonus/website/conf/* /var/www/

# EXPOSE 80
# CMD ["nginx", "-g", "daemon off;"]
