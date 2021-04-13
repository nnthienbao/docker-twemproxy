FROM golang:1.11.4 as builder
WORKDIR /usr/src

RUN git clone 'https://github.com/stuartnelson3/twemproxy_exporter.git'

RUN cd twemproxy_exporter && go get && make

FROM scratch
COPY --from=builder /usr/src/twemproxy_exporter/twemproxy_exporter /go/bin/twemproxy_exporter
COPY --from=builder /etc/ssl/certs/ca-certificates.crt /etc/ssl/certs/
ENTRYPOINT ["/go/bin/twemproxy_exporter"]