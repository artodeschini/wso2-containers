FROM postgres:9.4

ENV USR_LOCAL /usr/local

RUN mkdir -p "$USR_LOCAL"

WORKDIR $USR_LOCAL

ENV WSO2_UTILITIES $USR_LOCAL/utilities
ENV POSTGRES_JDBC_VERSION 9.4-1201.jdbc4

RUN apt-get install -y \
        curl \
        unzip

RUN curl -LOk https://jdbc.postgresql.org/download/postgresql-$POSTGRES_JDBC_VERSION.jar \
        && mv postgresql-$POSTGRES_JDBC_VERSION.jar $WSO2_UTILITIES/postgresql-$POSTGRES_JDBC_VERSION.jar
