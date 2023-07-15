FROM maven as maven_build
WORKDIR /app
COPY pom.xml /app
COPY src /app
RUN mvn clean install

FROM openjdk:11 as java_runTime
WORKDIR /jspring
COPY --from=maven_build /app/target/*.jar	/jspring/javaspringbt.jar
ENTRYPOINT ["java", "-jar", "app.jar"]
