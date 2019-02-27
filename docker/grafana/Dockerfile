FROM fg2it/grafana-armhf:v4.6.3
MAINTAINER Stefan Walther <swrnixda@gmail.com>

RUN apt-get update && \
    apt-get install -y curl gettext-base && \
    rm -rf /var/lib/apt/lists/*

COPY ./config/dashboards /opt/grafana-dashboards
COPY ./config/datasources /opt/grafana/datasources

WORKDIR /app
COPY entrypoint.sh ./
RUN chmod u+x entrypoint.sh

ENTRYPOINT ["/app/entrypoint.sh"]
