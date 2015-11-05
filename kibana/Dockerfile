FROM kibana:latest

RUN apt-get update && apt-get install -y netcat
RUN bin/kibana plugin --install elasticsearch/marvel/latest

COPY entrypoint.sh /tmp/entrypoint.sh
RUN chmod +x /tmp/entrypoint.sh

EXPOSE 5601

CMD ["/tmp/entrypoint.sh"]
