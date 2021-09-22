FROM ghcr.io/telekom-security/conpot:2006

USER root

ADD dist/ /root/dist/

RUN cp /root/dist/conpot.cfg /etc/conpot/conpot.cfg
RUN cp -R /root/dist/templates /usr/lib/python3.8/site-packages/conpot/
RUN rm -rf /root/*

STOPSIGNAL SIGINT
USER conpot:conpot
CMD exec /usr/bin/conpot --mibcache $CONPOT_TMP --temp_dir $CONPOT_TMP --template $CONPOT_TEMPLATE --logfile $CONPOT_LOG --config $CONPOT_CONFIG
