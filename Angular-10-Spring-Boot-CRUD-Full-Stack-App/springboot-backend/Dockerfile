FROM openjdk:8-jdk-alpine
VOLUME /tmp
ARG DEPENDENCY=target/dependency
COPY ${DEPENDENCY}/BOOT-INF/lib /app/lib
COPY ${DEPENDENCY}/META-INF /app/META-INF
COPY ${DEPENDENCY}/BOOT-INF/classes /app
#the below command is running main class with all the lib(*) at classpath
ENTRYPOINT ["java","-cp","app:app/lib/*","com.tutorial.springboot.SpringbootBackendApplication"]