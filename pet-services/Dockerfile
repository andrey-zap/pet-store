FROM maven:3.6.0-jdk-12-alpine as baseImage
COPY . /app
WORKDIR /app
RUN mvn install -Dmaven.test.skip=true

FROM openjdk:8-jdk-alpine
COPY --from=baseImage  /app/target/pet-services-1.0.0.jar /app/
WORKDIR /app
CMD ["java", "-jar","pet-services-1.0.0.jar"]
