FROM java:8
MAINTAINER demo@test.io
ENV MYPATH /root
WORKDIR $MYPATH
VOLUME $MYPATH
ARG JAR_FILE=app.jar
COPY ${JAR_FILE} app.jar
RUN ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
RUN echo 'Asia/Shanghai' >/etc/timezone
EXPOSE 9999
ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom","-jar","app.jar"]
