FROM ubuntu:20.04

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    libaio1 \
    locales \
    tzdata \
    && rm -rf /var/lib/apt/lists/*

# Locales
ADD locale /etc/default/locale
RUN locale-gen en_US.UTF-8
ENV LANG en_US.UTF-8
ENV LANGUAGE en_US:en
ENV LC_ALL en_US.UTF-8
RUN update-locale

# Timezone
RUN dpkg-reconfigure -f noninteractive tzdata

# Oracle
ENV ORACLE_HOME=/opt/oracle/instantclient_12_2
ENV LD_LIBRARY_PATH=${ORACLE_HOME}
ADD instantclient_12_2 ${ORACLE_HOME}
RUN ln -s ${ORACLE_HOME}/libclntsh.so.12.1 ${ORACLE_HOME}/libclntsh.so
RUN ln -s ${ORACLE_HOME}/libocci.so.12.1 ${ORACLE_HOME}/libocci.so
