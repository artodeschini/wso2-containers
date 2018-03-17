FROM java:7

ENV USR_LOCAL /usr/local

RUN mkdir -p "$USR_LOCAL"

WORKDIR $USR_LOCAL

ENV WSO2_BPS_VERSION 3.5.0-SNAPSHOT
ENV PRODUCT_NAME wso2bps

ENV PATH $USR_LOCAL/$PRODUCT_NAME/bin:$PATH

RUN apt-get install -y \
        curl \
        unzip

ENV WSO2_BPS_ZIP_URL https://svn.wso2.org/repos/wso2/people/warunaj/releases/bps350/M6/$PRODUCT_NAME-$WSO2_BPS_VERSION.zip

RUN curl -LOk $WSO2_BPS_ZIP_URL \
        && unzip -qq $PRODUCT_NAME-$WSO2_BPS_VERSION.zip \
        && rm $PRODUCT_NAME-$WSO2_BPS_VERSION/bin/*.bat \
        && rm wso2*.zip

RUN mv $PRODUCT_NAME-$WSO2_BPS_VERSION $PRODUCT_NAME

ENV JAVA_HOME /usr/lib/jvm/java-7-openjdk-amd64

EXPOSE ${WSO2_PORT:-9443}

CMD wso2server.sh -DportOffset=${WSO2_PORT_OFFSET:-0} console
