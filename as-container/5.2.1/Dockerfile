FROM java:7

ENV USR_LOCAL /usr/local

RUN mkdir -p "$USR_LOCAL"

WORKDIR $USR_LOCAL

ENV WSO2_AS_VERSION 5.2.1
ENV PRODUCT_NAME wso2as

ENV PATH $USR_LOCAL/$PRODUCT_NAME/bin:$PATH

RUN apt-get install -y \
        curl \
        unzip

ENV WSO2_AS_ZIP_URL http://product-dist.wso2.com/products/application-server/$WSO2_AS_VERSION/$PRODUCT_NAME-$WSO2_AS_VERSION.zip

RUN curl -LOk -A "testuser" -e "http://connect.wso2.com/wso2/getform/reg/new_product_download" $WSO2_AS_ZIP_URL \
        && unzip -qq $PRODUCT_NAME-$WSO2_AS_VERSION.zip \
        && rm $PRODUCT_NAME-$WSO2_AS_VERSION/bin/*.bat \
        && rm wso2*.zip

RUN mv $PRODUCT_NAME-$WSO2_AS_VERSION $PRODUCT_NAME

ENV JAVA_HOME /usr/lib/jvm/java-7-openjdk-amd64

EXPOSE ${WSO2_PORT:-9443}

CMD wso2server.sh -DportOffset=${WSO2_PORT_OFFSET:-0} console
