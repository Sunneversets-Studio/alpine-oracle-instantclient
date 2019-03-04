FROM debian:8-slim

EXPOSE 5000

COPY instantclient_12_1.zip ./

RUN apt-get update && \
    apt-get install -y libaio1 unzip && \
    unzip instantclient_12_1.zip && \
    mv instantclient_12_1/ /usr/lib/ && \
    rm instantclient_12_1.zip && \
    apt-get remove -y unzip && \
    ln -s /usr/lib/instantclient_12_1/libclntsh.so.12.1 /usr/lib/libclntsh.so && \
    ln -s /usr/lib/instantclient_12_1/libocci.so.12.1 /usr/lib/libocci.so && \
    ln -s /usr/lib/instantclient_12_1/libociei.so /usr/lib/libociei.so && \
    ln -s /usr/lib/instantclient_12_1/libnnz12.so /usr/lib/libnnz12.so && \
    ln -s /usr/lib/libnsl.so.2.0.0 /usr/lib/libnsl.so.1

ENV ORACLE_BASE /usr/lib/instantclient_12_1
ENV LD_LIBRARY_PATH lib:/usr/lib/instantclient_12_1
ENV TNS_ADMIN /usr/lib/instantclient_12_1
ENV ORACLE_HOME /usr/lib/instantclient_12_1
