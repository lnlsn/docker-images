FROM 0x7cc/deb-sbcl
MAINTAINER Lenilson Jose Dias <to@ha-ha.dev>

RUN sbcl --noinform --eval '(ql:quickload :coleslaw)' --eval '(quit)'

CMD ["sbcl"]
