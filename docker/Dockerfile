FROM andreptb/maven:3.3.9-jdk8-alpine

RUN mkdir -p /opt
WORKDIR /opt

COPY . ./
RUN mvn package


FROM java:8-jdk-alpine

COPY --from=0 /opt/target/spring-petclinic-1.5.1.jar petclinic.jar

EXPOSE 8080
CMD ["java", "-jar", "petclinic.jar"]
