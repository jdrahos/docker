FROM lga-registry01.pulse.prod:5000/frolvlad/alpine-glibc:alpine-3.5

RUN apk add --no-cache --virtual=build-dependencies curl ca-certificates && \
    mkdir -p /usr/java && \
    curl -jksSLH "Cookie: oraclelicense=accept-securebackup-cookie" http://download.oracle.com/otn-pub/java/jdk/8u121-b13/e9e7ea248e2c4826b92b3f075a80e441/jdk-8u121-linux-x64.tar.gz | gunzip -c - | tar -xf - -C /usr/java && \
    ln -s /usr/java/jdk1.8.0_121 /usr/java/latest && \
    rm -rf /usr/java/latest/*src.zip \
	   /usr/java/latest/lib/missioncontrol \
	   /usr/java/latest/lib/visualvm \
	   /usr/java/latest/lib/*javafx* \
	   /usr/java/latest/jre/lib/plugin.jar \
	   /usr/java/latest/jre/lib/ext/jfxrt.jar \
	   /usr/java/latest/jre/bin/javaws \
	   /usr/java/latest/jre/lib/javaws.jar \
	   /usr/java/latest/jre/lib/desktop \
	   /usr/java/latest/jre/plugin \
	   /usr/java/latest/jre/lib/deploy* \
	   /usr/java/latest/jre/lib/*javafx* \
	   /usr/java/latest/jre/lib/*jfx* \
	   /usr/java/latest/jre/lib/amd64/libdecora_sse.so \
	   /usr/java/latest/jre/lib/amd64/libprism_*.so \
	   /usr/java/latest/jre/lib/amd64/libfxplugins.so \
	   /usr/java/latest/jre/lib/amd64/libglass.so \
	   /usr/java/latest/jre/lib/amd64/libgstreamer-lite.so \
	   /usr/java/latest/jre/lib/amd64/libjavafx*.so \
   	   /usr/java/latest/jre/lib/amd64/libjfx*.so && \
    apk del build-dependencies && \
    rm -fr /tmp/*

ENV JAVA_HOME /usr/java/latest
ENV PATH ${PATH}:${JAVA_HOME}/bin
