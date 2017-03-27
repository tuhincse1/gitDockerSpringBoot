FROM openjdk:latest
ENV JAVA_HOME              /usr/lib/jvm/java-8-openjdk-amd64
ENV JAVA_OPTS              ""
ENV PATH                   $PATH:$JAVA_HOME/bin
CMD  ./gradlew clean buildDocker
COPY ./target/gitdockerspringboot-1.0-SNAPSHOT.jar /usr/src/gitdockerspringboot-1.0-SNAPSHOT.jar
CMD java -jar /usr/src/gitdockerspringboot-1.0-SNAPSHOT.jar
