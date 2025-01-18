FROM gradle:7.6-jdk11 AS builder

ENV POSTGRES_USER=kodilla

ENV POSTGRES_PASSWORD=kodilla

ENV POSTGRES_DB=kodilla-quotes

WORKDIR /app

COPY . .

RUN ./gradlew clean build

FROM openjdk:11-jdk-slim

COPY --from=builder /app/build/libs/quotes-0.0.1-SNAPSHOT.jar app.jar

EXPOSE 8080

ENTRYPOINT ["java", "-jar", "/app.jar"]
