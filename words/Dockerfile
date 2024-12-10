#Optimisation : Multi-stage build, image de base alpine plus légère

FROM maven:3.8.6-openjdk-11-slim AS builder

COPY . .

RUN mvn verify

FROM openjdk:11-jre-slim

COPY --from=builder ./target/words.jar ./target/words.jar
CMD ["java", "-Xmx8m", "-Xms8m", "-jar", "words.jar"]

EXPOSE 8080     