# Spring PetClinic Sample Application

## Run Petclinic locally

Spring Petclinic is a Spring Boot application built using Maven or Gradle.
You can build a jar file and run it from the command line (Java 17 or newer):

    git clone https://github.com/spring-projects/spring-petclinic.git
    cd spring-petclinic
    ./mvnw package
    java -jar target/*.jar

Petclinic will be available at http://localhost:8080/.

Or you can run it from Maven directly:

    ./mvnw spring-boot:run

## Building a Container

Use Spring Boot's build plugin:

    ./mvnw spring-boot:build-image

## Database configuration

By default, it uses an in-memory database (H2). For MySQL or PostgreSQL,
you can run:

    docker run -e MYSQL_USER=petclinic -e MYSQL_PASSWORD=petclinic \
      -e MYSQL_ROOT_PASSWORD=root -e MYSQL_DATABASE=petclinic \
      -p 3306:3306 mysql:9.1

    docker run -e POSTGRES_USER=petclinic -e POSTGRES_PASSWORD=petclinic \
      -e POSTGRES_DB=petclinic -p 5432:5432 postgres:17.0
