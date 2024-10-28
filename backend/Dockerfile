FROM maven:3.9.9-openjdk-21 AS build

WORKDIR /app

COPY ./app/pom.xml ./
RUN mvn dependency:go-offline

COPY ./app .

RUN mvn clean install

FROM openjdk:21-jre-slim

WORKDIR /app

COPY --from=build /app/target/*.jar app.jar

EXPOSE 8080

CMD ["java", "-jar", "app.jar"]