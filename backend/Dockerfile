FROM eclipse-temurin:17-jdk-alpine

WORKDIR /app

COPY target/spring-boot-data-jpa-0.0.1-SNAPSHOT.jar /app/spring-boot-data-jpa-0.0.1-SNAPSHOT.jar

LABEL maintainer="BOUTOUMIT EL MEHDI" \
      version="1.0"

RUN addgroup -S spring && adduser -S spring -G spring

RUN apk --no-cache upgrade --available openssl

RUN chown spring:spring /app/spring-boot-data-jpa-0.0.1-SNAPSHOT.jar

EXPOSE 8080

USER spring:spring

ENTRYPOINT ["java", "-jar", "spring-boot-data-jpa-0.0.1-SNAPSHOT.jar"]
CMD []

