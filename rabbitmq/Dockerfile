FROM rabbitmq:3.6.6-management-alpine

MAINTAINER Shaoping Liu <spieled916@gmail.com>

RUN	apk update && \
	apk add ca-certificates wget && \
	update-ca-certificates && \
	wget -O /plugins/rabbitmq_delayed_message_exchange-0.0.1.ez https://bintray.com/rabbitmq/community-plugins/download_file?file_path=rabbitmq_delayed_message_exchange-0.0.1.ez && \
	
# enable delayed
RUN rabbitmq-plugins enable rabbitmq_delayed_message_exchange
