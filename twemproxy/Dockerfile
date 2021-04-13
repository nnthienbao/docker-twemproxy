from ubuntu:14.04

WORKDIR /usr/src

RUN apt-get update

RUN apt-get install -y autoconf git libtool make

RUN git clone 'https://github.com/twitter/twemproxy.git'

RUN cd twemproxy && autoreconf -fvi && CFLAGS="-ggdb3 -O0" ./configure --enable-debug=log && make && make install

ENTRYPOINT [ "nutcracker" ]