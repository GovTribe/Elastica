FROM elasticsearch:2.1.1
MAINTAINER Nicolas Ruflin <spam@ruflin.com>

# Dependencies
ENV ES_MAPPER_ATTACHMENTS_VER 3.1.1
ENV ES_IMAGE_PLUGIN_VER 1.7.1
ENV ES_PLUGIN_BIN /usr/share/elasticsearch/bin/plugin

# Install Plugins
RUN ${ES_PLUGIN_BIN} install elasticsearch/elasticsearch-mapper-attachments/${ES_MAPPER_ATTACHMENTS_VER}
RUN ${ES_PLUGIN_BIN} install delete-by-query
#RUN ${ES_PLUGIN_BIN} install image --url https://github.com/Jmoati/elasticsearch-image/releases/download/${ES_IMAGE_PLUGIN_VER}/elasticsearch-image-${ES_IMAGE_PLUGIN_VER}.zip

# Debug interface
# RUN ${ES_PLUGIN_BIN} install mobz/elasticsearch-head

# Copy config files
COPY *.yml /usr/share/elasticsearch/config/
COPY scripts/* /usr/share/elasticsearch/config/scripts/


RUN mkdir -p /tmp/backups/backup1
RUN mkdir -p /tmp/backups/backup2

# Expose standard ports
EXPOSE 9200 9300
