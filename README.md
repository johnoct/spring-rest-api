# spring-rest-api

This is a simple rest api mini tutorial based on this guide here: https://spring.io/guides/gs/rest-service/

The purpose of this project was to learn more about the Spring framework and test the waters on REST API creation.

### Prerequisites

- JDK 1.8+
- Gradle 2.3+ or Maven 3.0+
- Your favourite IDE (I chose IntelliJ)

### Installing and Running

Clone this project:
```
git clone git@github.com:johnoct/spring-rest-api.git
```

Build and run the project:
```
cd spring-rest-api
mvn spring-boot:run
```

## Running the tests

Now you can go to your browser and visit the following:
```
http://localhost:8080/greeting
```

This should return:
```
{"id":1,"content":"Hello, World!"}
```

## Deployment

If we want to get fancy, we can actually build a Docker container with this REST API.

Build the JAR file:
```
mvn clean package
```

Run the JAR file:
```
java -jar target/gs-rest-service-0.1.0.jar
```

Create a dockerfile:
```
FROM java:8
WORKDIR /
ADD target/gs-rest-service-0.1.0.jar gs-rest-service-0.1.0.jar
EXPOSE 8080
CMD java -jar gs-rest-service-0.1.0.jar
```

Build the Docker image:
```
docker build -t spring-rest-api .
```

Run the Docker image:
```
docker run -p 8080:8080 spring-rest-api:latest
```



## Built With

* [Spring Getting Started](https://spring.io/guides/gs/rest-service/) - The Java framework used
* [Maven](https://maven.apache.org/) - Dependency Management
* [Docker](https://www.docker.com/) - Packaged and Containerized


## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* All credits go to the Spring Guides linked above
* I just wanted to start small and create a simple REST API and learn how to package it into a Docker Image from scratch
