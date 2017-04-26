FROM openjdk:latest
ENV JAVA_HOME              /usr/lib/jvm/java-8-openjdk-amd64
ENV JAVA_OPTS              ""
ENV PATH                   $PATH:$JAVA_HOME/bin
ENV TIME_ZONE              USA/Austin
ENV SPRING_PROFILES_ACTIVE test
RUN echo "$TIME_ZONE" > /etc/timezone
CMD  ./gradlew clean buildDocker
WORKDIR /target

EXPOSE 8080

ONBUILD COPY gitdockerspringboot-1.0-SNAPSHOT.jar /usr/src/gitdockerspringboot-1.0-SNAPSHOT.jar
CMD [java -jar /usr/src/gitdockerspringboot-1.0-SNAPSHOT.jar --spring.profiles.active=$SPRING_PROFILES_ACTIVE"]
CMD [docker run -e "SPRING_PROFILES_ACTIVE=test" -p 8080:8080 -t tuhincse1/gitdockerboot]
CMD [git clone git@github.com:tuhincse1/gitDockerSpringBoot.git ]
CMD [ cd gitDockerSpringBoot ; git tag v1.0 ; git push --tags ]
