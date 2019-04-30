FROM gliderlabs/alpine
MAINTAINER koenigphil@gmail.com
RUN mkdir /src
WORKDIR /src
RUN apk update && apk add bind-tools net-tools curl nmap jq tcpdump git

ENTRYPOINT ["sh"]
