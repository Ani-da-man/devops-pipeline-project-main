FROM eclipse-temurin:17-jre

WORKDIR /app

COPY files/devopsapp-1.1.jar app.jar

EXPOSE 8081

ENTRYPOINT ["java", "-jar", "app.jar", "--server.port=8081"]
