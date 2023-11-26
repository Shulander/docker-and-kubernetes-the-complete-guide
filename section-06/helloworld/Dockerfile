FROM openjdk:17-jdk-slim as build-phase

ENV BUILD_APP_HOME=/tmp/build
WORKDIR $BUILD_APP_HOME
COPY build.gradle settings.gradle gradlew $BUILD_APP_HOME
COPY gradle $BUILD_APP_HOME/gradle
COPY src ./src

RUN chmod +x gradlew && ./gradlew clean build --info
RUN pwd
RUN ls /tmp/build/build/libs

FROM openjdk:17-jdk-slim as app

WORKDIR /usr/app

COPY --from=build-phase /tmp/build/build/libs/helloworld-0.0.1-SNAPSHOT.jar ./app.jar

EXPOSE 8080
ENTRYPOINT ["java","-jar","app.jar"]

#Build: docker build . -t shulander/helloworld

#Mapping a port: docker run -p 8080:8080 shulander/helloworld
# above route the port from computer 8080 to docker image 8080
