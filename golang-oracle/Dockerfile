FROM golang:1.16

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    libaio1 libaio-dev \
    imagemagick zip unzip \
    locales \
    && rm -rf /var/lib/apt/lists/*

# Oracle
ENV ORACLE_HOME=/opt/oracle/instantclient_12_2
ENV LD_LIBRARY_PATH=${ORACLE_HOME}
ENV PKG_CONFIG_PATH=${ORACLE_HOME}
ADD instantclient_12_2 ${ORACLE_HOME}
RUN ln -s ${ORACLE_HOME}/libclntsh.so.12.1 ${ORACLE_HOME}/libclntsh.so
RUN ln -s ${ORACLE_HOME}/libocci.so.12.1 ${ORACLE_HOME}/libocci.so

# Package config
ADD oci8.pc ${ORACLE_HOME}/oci8.pc
