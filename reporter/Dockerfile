FROM ubuntu:22.10
		
RUN		apt-get -y update && apt-get -y upgrade		
RUN 	apt-get -y install wget gnupg curl

RUN wget -q -O - https://packages.grafana.com/gpg.key | apt-key add - && \
#add-apt-repository "deb https://packages.grafana.com/oss/deb stable main" && \
echo "deb https://packages.grafana.com/oss/deb stable main" | tee -a /etc/apt/sources.list.d/grafana.list &&\
apt-get  update && \
apt-get install grafana -y && \
update-rc.d grafana-server defaults


# Grafana
EXPOSE	3000

ENTRYPOINT service grafana-server start
