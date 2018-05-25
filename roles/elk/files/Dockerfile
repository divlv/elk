FROM sebp/elk

ADD ./03-gelf-input.conf /etc/logstash/conf.d/03-gelf-input.conf
ADD ./patterns/mycustomvars /etc/logstash/conf.d/patterns/mycustomvars
# TODO: add ADD directive to overwrite 30-output.conf as needed

# Use OSM and increase zoom level of map
RUN echo "tilemap.options.maxZoom: 18" >> /opt/kibana/config/kibana.yml
RUN echo "tilemap.url: http://a.tile.openstreetmap.org/{z}/{x}/{y}.png" >> /opt/kibana/config/kibana.yml

# expose GELF's default UDP port (12201)
EXPOSE 12201/udp
