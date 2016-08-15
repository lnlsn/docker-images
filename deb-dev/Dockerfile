FROM 0x7cc/deb-coleslaw
MAINTAINER Lenilson Jose Dias <lenilson@gmail.com>

ENV TERM xterm-256color

RUN apt-get update && apt-get install -y \
    netselect-apt

RUN netselect-apt -n jessie && \
    mv ./sources.list /etc/apt/sources.list && \
    apt-get update && \
    apt-get install -y \
	build-essential \
	bash-completion \
	emacs \
	xclip \
	tree \
	silversearcher-ag \
	colordiff \
	ncdu \
	&& apt-get clean

# container user
RUN groupadd -f -g 100 me && \
    useradd -s /bin/bash -u 1000 -g users me && \
    mkdir -p /home/me && \
    chown -R me:me /home/me

USER me

ADD quit.el /tmp

RUN git clone https://github.com/0x7cc/.emacs.d /home/me/.emacs.d && \
    cd /home/me/.emacs.d && \
    emacs --script /home/me/.emacs.d/setup-use-package.el && \
    emacs --script /tmp/quit.el

RUN mkdir /home/me/src/ && \
    git clone https://github.com/clvv/fasd /home/me/src/fasd && \
    cd /home/me/src/fasd && \
    PREFIX=$HOME make install


RUN git clone https://github.com/0x7cc/.nixsh /home/me/.nixsh && \
    echo '. /usr/lib/git-core/git-sh-prompt' >> /home/me/.bashrc && \
    echo '. ~/.nixsh/init.bash' >> /home/me/.bashrc