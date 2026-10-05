FROM maven:3.9.9-eclipse-temurin-8 AS build
WORKDIR /workspace
COPY pom.xml .
COPY discovery-server/pom.xml discovery-server/pom.xml
COPY discovery-server/src discovery-server/src
RUN mvn -q -pl discovery-server -am package -DskipTests
FROM eclipse-temurin:8-jre
WORKDIR /app
COPY --from=build /workspace/discovery-server/target/discovery-server-1.0.0.jar app.jar
ENTRYPOINT ["java","-jar","/app/app.jar"]
