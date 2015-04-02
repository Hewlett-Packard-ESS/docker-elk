FROM hpess/logstash:master
ENV http_proxy=http://16.85.88.10:8080
ENV https_proxy=http://16.85.88.10:8080
RUN /opt/logstash/bin/plugin install logstash-codec-cef
RUN echo "[service:logs]\ncommand=sleep infinity" > /etc/supervisord.d/sleep.service.conf
