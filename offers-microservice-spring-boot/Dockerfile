FROM openjdk:17
WORKDIR /app
COPY target/*.jar .
Expose 8761
CMD ["java", "-jar", "*.jar"]
