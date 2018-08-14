FROM openjdk:8-jdk-alpine
VOLUME  /opt/WDN
#RUN apk --no-cache add netcat-openbsd
#COPY target/webapp-0.0.1-SNAPSHOT.jar /opt/microservices/lib/app.jar
COPY entrypoint.sh /opt/WDN/microservices/scripts/entrypoint.sh
RUN chmod 755 /opt/WDN/microservices/scripts/entrypoint.sh
RUN dos2unix /opt/WDN/microservices/scripts/entrypoint.sh

COPY maven/ /opt/WDN/microservices/lib/

#ENV JAVA_OPTS="-XX:+UnlockExperimentalVMOptions -XX:+UseCGroupMemoryLimitForHeap  -XX:MaxRAMFraction=1 -XshowSettings:vm -Dspring.profiles.active=docker"
#ENV JAVA_OPTS="-Xms128m -Xmx256m -XshowSettings:vm -Dspring.profiles.active=docker"
ENTRYPOINT ["sh"]
CMD [ "-c","/opt/WDN/microservices/scripts/entrypoint.sh"]
#CMD [ "-c",  "java $JAVA_OPTS  -jar /opt/microservices/lib/app.jar"]
#EXPOSE 11000