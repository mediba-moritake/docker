FROM centos:6.6

RUN yum -y update

RUN yum install -y wget tar

ENV KIBANA_PKG_NAME kibana-4.1.4-linux-x64
RUN cd /
RUN wget https://download.elastic.co/kibana/kibana/$KIBANA_PKG_NAME.tar.gz
RUN tar xvzf $KIBANA_PKG_NAME.tar.gz
RUN rm -f $KIBANA_PKG_NAME.tar.gz
RUN mv /$KIBANA_PKG_NAME /kibana
RUN cp /kibana/config/kibana.yml /kibana/config/kibana.yml.org
ADD kibana.yml /kibana/config/

CMD ["/kibana/bin/kibana"]

EXPOSE 5601
