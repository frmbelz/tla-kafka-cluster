FROM confluentinc/cp-zookeeper:5.5.1

RUN apt-get update && apt-get install -y gettext

ARG KAFKA_SASL_USER
ARG KAFKA_SASL_PASS

ADD config/zookeeper.txt /tmp/kafka/zookeeper.temp

RUN cat /tmp/kafka/zookeeper.temp \
	| envsubst '$KAFKA_SASL_USER' \
	| envsubst '$KAFKA_SASL_PASS' \
	| tee /tmp/kafka/zookeeper.txt

