FROM maven:3.8.5-openjdk-17 AS build

WORKDIR /app

COPY . .

RUN mvn clean package -DskipTests

FROM openjdk:17-jdk-alpine

WORKDIR /app

COPY --from=build /app .

ENTRYPOINT ["mvn", "spring-boot:run"]