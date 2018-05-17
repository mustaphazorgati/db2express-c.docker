# Use an official Python runtime as a parent image
FROM ibmcom/db2express-c

RUN su - db2inst1 -c "db2start && db2 create database TSKDB using codeset utf-8 territory en-us collate using 'UCA500R1_CX' PAGESIZE 32 K" \
    && su - db2inst1 -c "db2stop force"

ENV DB2INST1_PASSWORD db2inst1-pwd

ENV LICENSE accept

EXPOSE 50000

COPY docker-entrypoint.sh /entrypoint.sh
CMD ["/entrypoint.sh"]
