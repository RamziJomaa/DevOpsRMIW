# Runtime léger pour Spring Boot (Java 17)
FROM eclipse-temurin:17-jre-alpine

WORKDIR /app

# Jar repackage par spring-boot-maven-plugin
COPY target/student-management-0.0.1-SNAPSHOT.jar app.jar

# Port Spring Boot
EXPOSE 8080

# Paramètres JVM
ENV JAVA_OPTS="-XX:+UseContainerSupport -Dfile.encoding=UTF-8"

# Entrée
ENTRYPOINT ["sh", "-c", "java $JAVA_OPTS -jar /app/app.jar"]
