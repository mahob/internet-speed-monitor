FROM python:3-alpine
WORKDIR /usr/speedtest
RUN pip install --no-cache-dir speedtest-cli && \
    speedtest-cli --csv-header > speedtest-results.csv && \
    # speedtest-cli --list
    # 16633) Stadtwerke Schorndorf GmbH (Schorndorf, Germany)
    echo "*/5 * * * * speedtest-cli --server 16633 --secure --csv >> /usr/speedtest/speedtest-results.csv" > /etc/crontabs/root
CMD ["crond", "-f", "-d", "8"]