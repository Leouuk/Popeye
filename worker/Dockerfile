#FIRST STAGE - COMPILATION
FROM maven:3.8.4-jdk-11-slim AS builder
WORKDIR /app
COPY . .
RUN mvn dependency:resolve
RUN mvn package

#SECOND STAGE - RUN
FROM openjdk:11-jre-slim
COPY --from=builder app/target/worker-jar-with-dependencies.jar .
CMD [ "java", "-jar", "target/worker-jar-with-dependencies.jar" ]