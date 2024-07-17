FROM fluentd:v1.14-1
USER root
# copy fluentd configuration from host image
COPY fluent.conf /fluentd/etc/
# copy binary start file
COPY entrypoint.sh /bin/
RUN chmod +x /bin/entrypoint.sh

RUN apk update \
  && gem install faraday-net_http -v 3.0.2 \
  && gem install faraday -v 2.8.1 \
  && gem install fluent-plugin-elasticsearch \
  && gem sources --clear-all \

USER fluent
