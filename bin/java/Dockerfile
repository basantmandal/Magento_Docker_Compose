FROM openjdk:17-oracle

RUN mkdir -p /opt/app

# Set working directory
WORKDIR /opt/app

# Bundle app source into container
COPY . .

# Expose the port the app runs in
EXPOSE 8887
