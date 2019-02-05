FROM node

ENV HOME=/home/yodauser

USER root

COPY ./contrib /usr/local/bin

RUN chown -R 1001:0 /opt/yoda && \
  /usr/local/bin/fix-permissions /opt/yoda && \
  /usr/local/bin/fix-permissions $HOME

USER 1001
WORKDIR $HOME
