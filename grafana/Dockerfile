FROM debian:jessie
MAINTAINER matthys.meintjes@bhpbilliton.com

ENV GRAFANA_VERSION 3.1.1-1470047149

ENV https_proxy $https_proxy
ENV http_proxy $http_proxy
ENV HTTPS_PROXY $https_proxy
ENV HTTP_PROXY $http_proxy

RUN apt-get update && apt-get -y --no-install-recommends install\
    libfontconfig\
    curl\
    ca-certificates && \
    apt-get clean && rm -rf /tmp/* /var/tmp/*

RUN  curl https://grafanarel.s3.amazonaws.com/builds/grafana_${GRAFANA_VERSION}_amd64.deb > /tmp/grafana.deb && \
    dpkg -i /tmp/grafana.deb && \
    rm /tmp/grafana.deb

RUN curl -L https://github.com/tianon/gosu/releases/download/1.7/gosu-amd64 > /usr/sbin/gosu && chmod +x /usr/sbin/gosu

# plugins
# datasource
RUN grafana-cli plugins install fetzerch-sunandmoon-datasource
RUN grafana-cli plugins install grafana-simple-json-datasource
# panels
RUN grafana-cli plugins install grafana-worldmap-panel
RUN grafana-cli plugins install grafana-piechart-panel
RUN grafana-cli plugins install briangann-gauge-panel
RUN grafana-cli plugins install jdbranham-diagram-panel
RUN grafana-cli plugins install savantly-heatmap-panel
# apps
RUN grafana-cli plugins install raintank-worldping-app
RUN grafana-cli plugins install percona-percona-app


EXPOSE 3000

COPY ./entrypoint.sh /entrypoint.sh
ENTRYPOINT ["/entrypoint.sh"]
