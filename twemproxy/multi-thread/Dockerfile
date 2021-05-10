from ubuntu:14.04

WORKDIR /usr/src

RUN apt-get update

RUN apt-get install -y autoconf git libtool make

RUN git clone 'https://github.com/vipshop/twemproxies.git'

RUN cd twemproxies && autoreconf -fvi && ./configure --enable-debug=log && make && src/nutcrackers -h

ENTRYPOINT [ "twemproxies/src/nutcrackers" ]