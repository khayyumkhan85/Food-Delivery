FROM maven:3.9.9-eclipse-temurin-8 AS build
WORKDIR /workspace
COPY pom.xml .
COPY restaurant-service/pom.xml restaurant-service/pom.xml
COPY restaurant-service/src restaurant-service/src
RUN mvn -q -pl restaurant-service -am package -DskipTests
FROM eclipse-temurin:8-jre
WORKDIR /app
COPY --from=build /workspace/restaurant-service/target/restaurant-service-1.0.0.jar app.jar
ENTRYPOINT ["java","-jar","/app/app.jar"]
