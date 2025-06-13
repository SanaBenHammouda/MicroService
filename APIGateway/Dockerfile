# Étape 1 : Builder avec Maven
FROM maven:3.9.0-eclipse-temurin-17 AS builder

# Créer un dossier de travail
WORKDIR /app

# Copier le pom.xml et les sources
COPY pom.xml .
COPY src ./src

# Build du projet Spring Boot
RUN mvn clean package -DskipTests


# Étape 2 : Image finale
FROM eclipse-temurin:17-jdk-jammy

WORKDIR /app

# Copier le JAR depuis le builder
COPY --from=builder /app/target/gateway-service-0.0.1-SNAPSHOT.jar ./gateway-service.jar

# Exposer le port utilisé par le Gateway (8088)
EXPOSE 8088

# Lancer le Gateway
ENTRYPOINT ["java", "-jar", "gateway-service.jar"]
