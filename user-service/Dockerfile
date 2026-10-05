FROM maven:3.9.9-eclipse-temurin-8 AS build
WORKDIR /workspace
COPY pom.xml .
COPY user-service/pom.xml user-service/pom.xml
COPY user-service/src user-service/src
RUN mvn -q -pl user-service -am package -DskipTests
FROM eclipse-temurin:8-jre
WORKDIR /app
COPY --from=build /workspace/user-service/target/user-service-1.0.0.jar app.jar
ENTRYPOINT ["java","-jar","/app/app.jar"]
