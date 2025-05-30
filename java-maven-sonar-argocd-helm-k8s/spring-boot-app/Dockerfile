# Start from Maven image with Java 17 Temurin
FROM maven:3.8.8-eclipse-temurin-17

USER root

# Install Docker CLI and other tools using apt-get
RUN apt-get update && apt-get install -y \
    docker.io \
    bash \
    curl \
    && rm -rf /var/lib/apt/lists/*

# Set working directory for your app
WORKDIR /opt/app

# Copy artifact argument (can be overridden during build)
ARG artifact=target/spring-boot-web.jar

# Copy the artifact (your Spring Boot JAR)
COPY ${artifact} app.jar

# Default entrypoint to run your app
ENTRYPOINT ["java", "-jar", "app.jar"]


