FROM openjdk:8u191-jre-alpine3.9
ENTRYPOINT ["/usr/bin/java", "-jar", "/app.jar"]
ADD app.jar /app.jar
RUN ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
RUN echo 'Asia/Shanghai' >/etc/timezone
EXPOSE 9999