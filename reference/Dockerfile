FROM java:8
MAINTAINER demo@test.io
ENV MYPATH /
WORKDIR $MYPATH
ARG JAR_FILE=dubbo-starter-reference-0.0.1-SNAPSHOT.jar
COPY ${JAR_FILE} dubbo-starter-reference-0.0.1-SNAPSHOT.jar
RUN ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
RUN echo 'Asia/Shanghai' >/etc/timezone
EXPOSE 9997
EXPOSE 20881
ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom","-jar","dubbo-starter-reference-0.0.1-SNAPSHOT.jar"]
