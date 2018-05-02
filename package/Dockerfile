# clcos-ui Docker File
FROM ubuntu:16.04

MAINTAINER Dennis Sun <dennis-sun@live.cn>

RUN rm /bin/sh && ln -s /bin/bash /bin/sh

#设置系统源路径

RUN sed -i 's/http:\/\/archive\.ubuntu\.com\/ubuntu\//http:\/\/mirrors\.163\.com\/ubuntu\//g' /etc/apt/sources.list


##安装依赖包
RUN apt-get update && apt-get install --no-install-recommends -y curl ca-certificates vim wget bash-completion openjdk-8-jre tree


VOLUME /tmp
ADD eurekaserver.jar app.jar
RUN sh -c 'touch /app.jar'

EXPOSE 8761

ENTRYPOINT [ "sh", "-c", "java $JAVA_OPTS -Djava.security.egd=file:/dev/./urandom -jar /app.jar" ]


