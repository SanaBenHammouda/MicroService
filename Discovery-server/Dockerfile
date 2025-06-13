# Utiliser une image JDK 17 (ou celle compatible avec ton projet)
FROM eclipse-temurin:17-jdk-jammy

# Répertoire de travail dans le container
WORKDIR /app

# Copier le jar construit dans le container
COPY target/discovery-server.jar discovery-server.jar

# Exposer le port 8761 (celui de Eureka)
EXPOSE 8761

# Commande pour lancer l'application
ENTRYPOINT ["java", "-jar", "discovery-server.jar"]
