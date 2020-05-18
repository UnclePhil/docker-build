FROM alpine:latest

RUN apk --no-cache add ca-certificates wget tar nginx \
 && wget -O freeboard.tar.gz https://api.github.com/repos/Freeboard/freeboard/tarball/master \
 && mkdir -p /usr/share/nginx/html/plugins/mqtt \
 && mkdir -p /usr/share/nginx/html/plugins/thirdparty \
 && mkdir /run/nginx \
 && tar -xzvf freeboard.tar.gz -C /usr/share/nginx/html --strip-components=1 \
 && rm freeboard.tar.gz

COPY src/default.conf /etc/nginx/conf.d/default.conf
COPY src/paho.mqtt.plugin.js /usr/share/nginx/html/plugins/thirdparty/
COPY src/mqttws31.js /usr/share/nginx/html/plugins/mqtt/
COPY src/index.html /usr/share/nginx/html/
COPY src/dashboard.json /usr/share/nginx/html/

STOPSIGNAL SIGTERM
CMD ["nginx", "-g", "daemon off;"]
