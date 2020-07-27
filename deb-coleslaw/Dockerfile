FROM lnlsn/deb-sbcl
MAINTAINER Lenilson Jose Dias <to@lnlsn.dev>

RUN sbcl --noinform --eval '(ql:quickload :coleslaw)' --eval '(quit)'

CMD ["sbcl"]
