FROM centos:6.6

RUN yum -y update

RUN yum install -y wget tar

RUN yum install -y java-1.8.0-openjdk
ENV JAVA_HOME /usr/lib/jvm/jre-1.8.0-openjdk.x86_64
ENV PATH $PATH:$JAVA_HOME/bin
ENV CLASSPATH=.:$JAVA_HOME/jre/lib:$JAVA_HOME/lib:$JAVA_HOME/lib/tools.jar

ENV ES_PKG_NAME elasticsearch-1.7.4
RUN cd /
RUN wget https://download.elasticsearch.org/elasticsearch/elasticsearch/$ES_PKG_NAME.tar.gz
RUN tar xvzf $ES_PKG_NAME.tar.gz
RUN rm -f $ES_PKG_NAME.tar.gz
RUN mv /$ES_PKG_NAME /elasticsearch

CMD ["/elasticsearch/bin/elasticsearch"]

RUN /elasticsearch/bin/plugin install elasticsearch/elasticsearch-analysis-kuromoji/2.7.0
RUN /elasticsearch/bin/plugin -install mobz/elasticsearch-head

EXPOSE 9200
