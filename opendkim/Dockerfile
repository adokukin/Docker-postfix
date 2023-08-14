FROM alpine:3.14

# update / upgrade / add
RUN \
	apk update --no-cache && \
	apk upgrade --no-cache && \
	apk add --no-cache bash opendkim opendkim-utils ca-certificates

# openkim
COPY ./conf/ /etc/opendkim/
RUN mkdir /etc/opendkim/keys

# startup
CMD /usr/sbin/opendkim -x /etc/opendkim/opendkim.conf -f

EXPOSE 12301
