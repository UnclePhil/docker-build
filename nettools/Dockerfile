FROM gliderlabs/alpine
MAINTAINER koenigphil@gmail.com
RUN mkdir /src
WORKDIR /src
RUN apk update && apk add bind-tools net-tools curl nmap jq tcpdump git && \
    git clone https://github.com/trimstray/htrace.sh && \
    cd htrace.sh && build/build.sh

ENTRYPOINT ["sh"]
