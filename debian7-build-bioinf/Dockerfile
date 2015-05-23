FROM debian:7
MAINTAINER Kevin Murray <spam@kdmurray.id.au>

RUN apt-get update
RUN apt-get upgrade -y
RUN apt-get install -y \
	build-essential \
	cmake \
	git \
	libbz2-dev \
	python-pip \
	wget \
	zlib1g-dev

#### Install general bioinformaitcs libaries ####

RUN mkdir -p /usr/local/{bin,lib,share,include,etc,src}

RUN cd /usr/local/src

# seqan
RUN wget 'https://github.com/seqan/seqan/archive/seqan-v2.0.0.tar.gz'
RUN tar xvf seqan-v2.0.0.tar.gz
RUN cp -r seqan-seqan-v2.0.0/include/seqan/ ../include/
RUN rm -r seqan-v2.0.0.tar.gz seqan-seqan-v2.0.0


# HTSlib
RUN wget 'https://github.com/samtools/htslib/releases/download/1.2.1/htslib-1.2.1.tar.bz2'
RUN tar xvf htslib-1.2.1.tar.bz2
RUN cd htslib-1.2.1/
RUN make && make install
RUN rm -r htslib-1.2.1.tar.bz2 htslib-1.2.1/
