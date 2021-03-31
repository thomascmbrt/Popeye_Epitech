FROM maven:3.5-jdk-8-alpine AS builder
COPY . .
RUN mvn dependency:resolve
RUN mvn package

FROM openjdk:8-jre-alpine
WORKDIR /target/
COPY --from=builder /target .
CMD ["java", "-jar", "worker-ajr-with-dependencies.jar"]