FROM docker.elastic.co/logstash/logstash:5.5.1

COPY logstash.yml /usr/share/logstash/config/
COPY logstash.conf /usr/share/logstash/pipeline/
COPY ./lib/mysql-connector-java-5.1.44-bin.jar /usr/shared/lib/

ENV ELASTICSEARCH_HOST=elasticsearch \
    ELASTICSEARCH_PORT=9200 \
    INPUT_TCP_PORT=5000 \
    INPUT_UDP_PORT=5000 \
    LOGSTASH_DEBUG=true

CMD logstash -f /usr/share/logstash/pipeline/logstash.conf