FROM alpine

RUN apk --update add rsync openssh && rm -rf /var/cache/apk/*
RUN touch /var/log/rsyncd.log 

EXPOSE 873

CMD crond -l 2 -b -L /var/log/crond.log && /usr/bin/rsync --daemon --config=/etc/rsyncd.conf && tail -f /var/log/rsyncd.log
