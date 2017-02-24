FROM coldrye/debian-tini:0-14-0-jessie-latest

RUN set -ex \
    && export APT_LISTCHANGES_FRONTEND=none \
    && apt-get update \
    && apt-get -q -y -o Dpkg::Options::="--force-confdef" -o Dpkg::Options::="--force-confold" -t jessie-backports install bind9 \
    && apt-get clean \
    && rm -Rf /var/lib/apt/lists/* 2>/dev/null

VOLUME ["/etc/bind"]

ENV PORT=53 PROTO=4 CPUS=1

CMD rm -f /var/run/named/named.pid && /usr/sbin/named -g -p $PORT -$PROTO -n $CPUS

