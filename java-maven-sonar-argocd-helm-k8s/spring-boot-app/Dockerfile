# Start from Maven image with Java 17 Temurin
FROM maven:3.8.8-eclipse-temurin-17

# Install Docker CLI (Alpine based, so use apk)
USER root

# Install Docker CLI
RUN apk add --no-cache \
    docker-cli \
    bash \
    curl \
    && rm -rf /var/cache/apk/*

# Set working directory for your app
WORKDIR /opt/app

# Copy artifact argument (can be overridden during build)
ARG artifact=target/spring-boot-web.jar

# Copy the artifact (your Spring Boot JAR)
COPY ${artifact} app.jar

# Default entrypoint to run your app
ENTRYPOINT ["java", "-jar", "app.jar"]

