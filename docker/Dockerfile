FROM tomcat:7.0.92-jre8-alpine

ENV CATALINA_HOME /usr/local/tomcat

WORKDIR $CATALINA_HOME

RUN rm -r $CATALINA_HOME/webapps/*
COPY ./cat-home/target/*.war $CATALINA_HOME/webapps/cat.war
COPY docker/datasources.xml /data/appdatas/cat/datasources.xml
COPY docker/datasources.sh /datasources.sh
RUN sed -i "s/port=\"8080\"/port=\"8080\"\ URIEncoding=\"utf-8\"/g" $CATALINA_HOME/conf/server.xml

EXPOSE 8080