# First build the application
FROM gliderlabs/alpine
RUN apk --no-cache add go git musl-dev
## RUN go get -u github.com/skx/dns-api-go
RUN git clone https://github.com/skx/dns-api-go
WORKDIR ./dns-api-go
RUN go install


# Now put it in a container without all the build tools
FROM gliderlabs/alpine
WORKDIR /root/
COPY --from=0 /root/go/bin/dns-api-go .
EXPOSE 9999
ENTRYPOINT ["/root/dns-api-go", "-host", "0.0.0.0", "-port", "9999" ]