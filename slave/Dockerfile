FROM amazoncorretto:8-alpine-jdk
		
ARG JMETER_VERSION=5.2.1

RUN apk update && apk add wget unzip

RUN   mkdir /jmeter \
&& cd /jmeter/ \
&& wget https://archive.apache.org/dist/jmeter/binaries/apache-jmeter-$JMETER_VERSION.tgz \
&& tar -xzf apache-jmeter-$JMETER_VERSION.tgz \
&& rm apache-jmeter-$JMETER_VERSION.tgz

ENV JMETER_HOME /jmeter/apache-jmeter-$JMETER_VERSION/
		
ENV PATH $JMETER_HOME/bin:$PATH

ENTRYPOINT $JMETER_HOME/bin/jmeter-server \
-Dserver.rmi.localport=50000 \
-Dserver_port=1099 \
-Jserver.rmi.ssl.disable=true