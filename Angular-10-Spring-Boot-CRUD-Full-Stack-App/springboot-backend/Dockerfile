FROM openjdk:8-jdk-alpine
VOLUME /tmp
ARG DEPENDENCY=target/dependency
COPY ${DEPENDENCY}/BOOT-INF/lib /app/lib
COPY ${DEPENDENCY}/META-INF /app/META-INF
COPY ${DEPENDENCY}/BOOT-INF/classes /app
ENV RDS_HOSTNAME=mypostgresdb.cfixz8qfw1zr.us-east-1.rds.amazonaws.com
ENV RDS_PORT=5432
ENV RDS_DB_NAME=employee_db
ENV RDS_USERNAME=postgres
ENV RDS_PASSWORD=postgres2021
#the below command is running main class with all the lib(*) at classpath
ENTRYPOINT ["java","-cp","app:app/lib/*","com.tutorial.springboot.SpringbootBackendApplication"]
