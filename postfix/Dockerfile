FROM alpine:3.14

# update / upgrade / add
RUN \
	apk update --no-cache && \
	apk upgrade --no-cache && \
	apk add --no-cache bash postfix ca-certificates

# postfix
COPY postfix.conf /etc/postfix/main-override.cf
RUN \
	cd /etc/postfix && \
	cat main.cf main-override.cf > main-sum.cf && \
	mv main-sum.cf main.cf && \
	rm main-override.cf

# startup
CMD /usr/sbin/postfix -c /etc/postfix start-fg

EXPOSE 25
