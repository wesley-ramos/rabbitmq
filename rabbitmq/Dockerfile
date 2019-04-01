FROM rabbitmq:3-management

RUN apt-get update && apt-get install -y --no-install-recommends ca-certificates wget 

RUN cd /plugins && \
	wget https://github.com/deadtrickster/prometheus_rabbitmq_exporter/releases/download/v3.7.2.5/accept-0.3.5.ez && \
	wget https://github.com/deadtrickster/prometheus_rabbitmq_exporter/releases/download/v3.7.2.5/prometheus-4.2.2.ez && \
	wget https://github.com/deadtrickster/prometheus_rabbitmq_exporter/releases/download/v3.7.2.5/prometheus_cowboy-0.1.7.ez && \
	wget https://github.com/deadtrickster/prometheus_rabbitmq_exporter/releases/download/v3.7.2.5/prometheus_httpd-2.1.10.ez && \
	wget https://github.com/deadtrickster/prometheus_rabbitmq_exporter/releases/download/v3.7.2.5/prometheus_process_collector-1.4.3.ez && \
	wget https://github.com/deadtrickster/prometheus_rabbitmq_exporter/releases/download/v3.7.2.5/prometheus_rabbitmq_exporter-3.7.2.5.ez

COPY rabbit.conf /etc/rabbitmq/rabbitmq.conf

RUN rabbitmq-plugins enable prometheus_rabbitmq_exporter && \
	rabbitmq-plugins enable prometheus_process_collector

EXPOSE 15672 5672 4369 25672
