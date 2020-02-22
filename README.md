# hakeep
HAProxy with Keepalived container.

**Feature:**

- **graceful_shutdown**: with `start.sh`, added graceful shutdown with it.

## Usage ([DockerHub](https://hub.docker.com/r/pelin/haproxy-keepalived/))

This image use host config file, and then run it:

```bash
docker run -it -d --net=host --privileged \
    -v ${HAPROXY_CONFIG_FILE}:/usr/local/etc/haproxy/haproxy.cfg \
    -v ${KEEPALIVED_CONFIG_FILE}:/etc/keepalived/keepalived.conf \
    --name haproxy-keepalived \
    haproxy-keepalived
