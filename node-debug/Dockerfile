FROM node

ENV HOME=/home/yodauser

USER root

RUN useradd -ms /bin/bash  yodauser

USER yodauser

RUN chown -R 1001:0 /usr/local/bin/fix-permissions $HOME

USER 1001
WORKDIR $HOME

EXPOSE 5900
