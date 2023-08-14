FROM alpine:3.14

# update / upgrade / add
RUN \
	apk update --no-cache && \
	apk upgrade --no-cache && \
	apk add --no-cache rsyslog bash

# rsyslog
COPY rsyslog.conf /etc/rsyslog.conf

# startup
CMD rsyslogd -n
VOLUME /dev
VOLUME /var/log
