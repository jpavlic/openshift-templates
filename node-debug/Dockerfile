FROM node

ENV HOME=/home/yodauser

USER root

COPY ./contrib /usr/local/bin

RUN useradd -ms /bin/bash  yodauser

RUN chown -R yodauser:0 /usr/local/bin/fix-permissions $HOME

USER yodauser
WORKDIR $HOME

EXPOSE 5900
