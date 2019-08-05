FROM tomcat

RUN apt-get update && apt-get install -y \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* \
    && mv /usr/local/tomcat/webapps /usr/local/tomcat/webapps_back \
    && mkdir /usr/local/tomcat/webapps
COPY conf/server.xml /usr/local/tomcat/conf/server.xml
COPY conf/ROOT /usr/local/tomcat/webapps/ROOT
EXPOSE 8090
