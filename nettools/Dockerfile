ARG SRC_IMG="gliderlabs/alpine"
FROM ${SRC_IMG}

## set some additional label
LABEL source="${SRC_IMG}"
LABEL owner="koenigphil@gmail.com"

RUN mkdir /src
WORKDIR /src
RUN apk update && apk add bind-tools net-tools curl nmap jq tcpdump git

ENTRYPOINT ["sh"]
