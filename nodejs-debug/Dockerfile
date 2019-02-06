FROM jpavlic/nodejs-debug

ENV HOME=/home/nodejsuser

USER root

COPY ./contrib /usr/local/bin

RUN /usr/local/bin/fix-permissions $HOME

USER 1001
WORKDIR $HOME

EXPOSE 5900
