FROM solr

WORKDIR /opt/solr

#RUN  ls server/solr/configsets/_default/conf/
#RUN  ls server/solr/configsets/


USER root
RUN mkdir server/solr/configsets/nutch/
#RUN mkdir server/solr/configsets/nutch/conf/
#RUN ls server/solr/configsets/nutch/conf/

RUN cp -r server/solr/configsets/_default/conf server/solr/configsets/nutch/
ADD conf/solr-mapping.xml server/solr/configsets/nutch/schema.xml
RUN rm server/solr/configsets/nutch/conf/managed-schema

RUN chown -R solr.solr server/solr/configsets/nutch/
USER solr