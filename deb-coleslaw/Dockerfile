FROM 0x7cc/deb-sbcl
MAINTAINER Lenilson Jose Dias <lenilson@gmail.com>

RUN sbcl --noinform --eval '(ql:quickload :coleslaw)' --eval '(quit)'

CMD ["sbcl"]
