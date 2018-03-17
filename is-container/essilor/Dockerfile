FROM java:7

ENV USR_LOCAL /usr/local

RUN mkdir -p "$USR_LOCAL"

WORKDIR $USR_LOCAL

ENV PRODUCT_NAME wso2is
ENV WSO2_IS_VERSION 5.0.0

ENV PATH $USR_LOCAL/$PRODUCT_NAME/bin:$PATH

RUN apt-get install -y \
        curl \
        git \
        unzip

ENV WSO2_IS_ZIP_URL http://product-dist.wso2.com/products/identity-server/$WSO2_IS_VERSION/$PRODUCT_NAME-$WSO2_IS_VERSION.zip

RUN curl -LOk -A "testuser" -e "http://connect.wso2.com/wso2/getform/reg/new_product_download" $WSO2_IS_ZIP_URL \
        && unzip -qq $PRODUCT_NAME-$WSO2_IS_VERSION.zip \
        && rm $PRODUCT_NAME-$WSO2_IS_VERSION/bin/*.bat \
        && rm wso2*.zip

RUN mv $PRODUCT_NAME-$WSO2_IS_VERSION $PRODUCT_NAME

ENV JAVA_HOME /usr/lib/jvm/java-7-openjdk-amd64

ENV OPT_TOMCAT /opt/tomcat
ENV TOMCAT_DIR_VERSION apache-tomcat-8.0.26
ENV CATALINA_HOME $OPT_TOMCAT/$TOMCAT_DIR_VERSION

RUN mkdir -p "$OPT_TOMCAT"

RUN curl -LOk http://mirror.nbtelecom.com.br/apache/tomcat/tomcat-8/v8.0.26/bin/$TOMCAT_DIR_VERSION.zip \
        && unzip -qq $TOMCAT_DIR_VERSION.zip \
        && mv $TOMCAT_DIR_VERSION $OPT_TOMCAT \
        && rm $TOMCAT_DIR_VERSION.zip

ENV MAVEN_DIR /usr/local/apache-maven
RUN mkdir -p $MAVEN_DIR

RUN curl -LOk http://ftp.unicamp.br/pub/apache/maven/maven-3/3.3.3/binaries/apache-maven-3.3.3-bin.zip \
        && unzip -qq apache-maven-3.3.3-bin.zip \
        && mv apache-maven-3.3.3 $MAVEN_DIR \
        && rm apache-maven-3.3.3-bin.zip

ENV M2_HOME $MAVEN_DIR/apache-maven-3.3.3
ENV M2 $M2_HOME/bin
ENV MAVEN_OPTS "-Xms256m -Xmx512m"
ENV PATH $M2:$PATH

ENV WSO2_IS_SSO_APP_PROJECT wso2-is-sso-app

RUN git clone https://github.com/brunocesarsilva/$WSO2_IS_SSO_APP_PROJECT.git \
        && cd $WSO2_IS_SSO_APP_PROJECT \
        && mvn clean package \
        && cd ..

RUN cp $WSO2_IS_SSO_APP_PROJECT/target/wso2sso.war $CATALINA_HOME/webapps

RUN rm -r $WSO2_IS_SSO_APP_PROJECT

RUN apt-get remove -y \
        curl \
        git \
        unzip

RUN apt-get clean

RUN rm -r $MAVEN_DIR \
        && rm -r ~/.m2

RUN chmod 777 $CATALINA_HOME/bin/*

EXPOSE 8080
EXPOSE ${WSO2_PORT:-9443}

CMD CATALINA_HOME/bin/startup.sh console
CMD wso2server.sh -DportOffset=${WSO2_PORT_OFFSET:-0} console
