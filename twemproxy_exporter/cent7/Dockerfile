FROM centos:7 as builder
WORKDIR /usr/src

RUN yum -y install git wget make

RUN wget https://dl.google.com/go/go1.13.linux-amd64.tar.gz
RUN tar -C /usr/local -xzf go1.13.linux-amd64.tar.gz

RUN git clone 'https://github.com/stuartnelson3/twemproxy_exporter.git'

RUN export PATH=$PATH:/usr/local/go/bin && cd twemproxy_exporter && go get && make

FROM scratch
COPY --from=builder /usr/src/twemproxy_exporter/twemproxy_exporter /go/bin/twemproxy_exporter
ENTRYPOINT ["/go/bin/twemproxy_exporter"]