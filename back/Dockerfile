FROM gradle:8.5.0-jdk21 AS build
COPY --chown=gradle:gradle . /home/gradle/project
WORKDIR /home/gradle/project
RUN gradle bootJar -x test

FROM eclipse-temurin:21-jdk-jammy as runtime
WORKDIR /app
COPY ./build/libs/e-commerce-0.0.1-SNAPSHOT.jar app.jar
ENTRYPOINT ["java", "-jar", "/app/app.jar"]