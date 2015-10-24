FROM tomcat:8-jre8

MAINTAINER Alejandro Gomez <ideaplugins [at] gmail [dot] com>

ENV UAA_CONFIG_PATH /uaa

ADD uaa.yml /uaa/uaa.yml

RUN rm -rf "$CATALINA_HOME/webapps/*"

ENV UAA_VERSION 2.7.0.3

RUN wget -q -O uaa.war "http://central.maven.org/maven2/org/cloudfoundry/identity/cloudfoundry-identity-app/$UAA_VERSION/cloudfoundry-identity-app-$UAA_VERSION.war"

RUN unzip -d "$CATALINA_HOME/webapps/uaa" uaa.war

RUN rm uaa.war

VOLUME ["/uaa"]

EXPOSE 8080

ENTRYPOINT ["catalina.sh", "run"]
