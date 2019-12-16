FROM debian:latest
MAINTAINER Lenilson Jose Dias <to@ha-ha.dev>

RUN apt-get update && apt-get install -y \
  curl	    \
  git	    \
  sbcl	    \
  && apt-get clean

RUN curl -O https://beta.quicklisp.org/quicklisp.lisp
ADD install-quicklisp.lisp /
RUN sbcl --script install-quicklisp.lisp

CMD ["sbcl"]
