FROM solr:6.3.0-alpine

MAINTAINER Martin Rumanek <martin@rumanek.cz>

USER root
ADD kramerius /kramerius
RUN chown -R $SOLR_USER:0 /kramerius && \
    chmod -R ug+rwX /kramerius && \
    chown -R $SOLR_USER:0 /opt/solr && \
    chmod -R ug+rwX /opt/solr && \
    chown -R $SOLR_USER:0 /opt/docker-solr && \
    chmod -R ug+rwX /opt/docker-solr
USER $SOLR_USER

#OAI config file is in conf folder of a core
ADD oai/lib /opt/solr/server/solr/lib
ADD oai/oai /opt/solr/server/solr/oai

CMD docker-entrypoint.sh solr-precreate  kramerius /kramerius 
