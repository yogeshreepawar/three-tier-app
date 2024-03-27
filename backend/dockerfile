FROM centos:7
LABEL docker="tomcat"
WORKDIR /opt
RUN yum install java -y
RUN curl -O https://dlcdn.apache.org/tomcat/tomcat-8/v8.5.99/bin/apache-tomcat-8.5.99.tar.gz
RUN tar -xvzf apache-tomcat-8.5.99.tar.gz -C /opt
WORKDIR /opt/apache-tomcat-8.5.99/webapps
RUN curl -O https://s3-us-west-2.amazonaws.com/studentapi-cit/student.war
WORKDIR /opt/apache-tomact-8.5.99/lib
RUN curl -O https://s3-us-west-2.amazonaws.com/studentapi-cit/mysql-connector.jar
COPY context.xml conf/context.xml
EXPOSE 8080
CMD ["/opt/apache-tomcat-8.5.99/bin/catalina.sh", "run"]