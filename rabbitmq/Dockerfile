FROM rabbitmq:3.6.6-management-alpine

MAINTAINER Shaoping Liu <spieled916@gmail.com>

RUN apk upgrade --update && \
    apk add --no-cache --virtual=build-dependencies wget && \
	wget -O /plugins/rabbitmq_delayed_message_exchange-0.0.1.ez https://bintray.com/rabbitmq/community-plugins/download_file?file_path=rabbitmq_delayed_message_exchange-0.0.1.ez && \
	
# enable delayed
RUN rabbitmq-plugins enable rabbitmq_delayed_message_exchange
