FROM maven:3-jdk-7

ENV USR_LOCAL /usr/local

RUN mkdir -p "$USR_LOCAL"

WORKDIR $USR_LOCAL

ENV PRODUCT_NAME wso2bps
ENV WSO2_BPS_PRODUCT_REPO product-bps
ENV WSO2_BPS_PRODUCT_GIT_CMD git clone https://github.com/wso2/$WSO2_BPS_PRODUCT_REPO

RUN apt-get install -y \
        git \
        unzip

# clona o repositório GIT a ser construido
RUN $WSO2_BPS_PRODUCT_GIT_CMD

# compila o repositório (demora pacas)
RUN cd $WSO2_BPS_PRODUCT_REPO \
        && mvn package -Dmaven.skip.tests=true

#
RUN mv $WSO2_BPS_PRODUCT_REPO/*.zip $USR_LOCAL

#
RUN cd $USR_LOCAL \
        && unzip -qq *.zip \
        && rm $PRODUCT_NAME/bin/*.bat \
        && rm wso2*.zip

# apaga os binários baixado pelo maven
RUN 

# apaga o repositório GIT clonado e todo o conteúdo gerado no build
RUN rm -r /$WSO2_BPS_PRODUCT_REPO

#

RUN mv $PRODUCT_NAME-$WSO2_BPS_VERSION $PRODUCT_NAME

ENV PATH $USR_LOCAL/$PRODUCT_NAME/bin:$PATH
ENV JAVA_HOME /usr/lib/jvm/java-7-openjdk-amd64

EXPOSE ${WSO2_PORT:-9443}

CMD wso2server.sh -DportOffset=${WSO2_PORT_OFFSET:-0} console
