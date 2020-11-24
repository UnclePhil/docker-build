## from brunopadz/mkcert-docker
## but for unclephil trusted collection
ARG SRC_IMG=golang:1.12-alpine
FROM ${SRC_IMG}
## set some additional label
LABEL source="${SRC_IMG}"
LABEL owner="koenigphil@gmail.com"

RUN apk --no-cache add git
RUN go get -u github.com/FiloSottile/mkcert
CMD ["mkcert"]
