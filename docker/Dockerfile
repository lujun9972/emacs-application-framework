FROM base/archlinux

RUN pacman -Syy && \
    pacman -S git emacs  nss python python-pip python-dbus  --noconfirm && \
    yes|pacman -Scc 

RUN pip install --upgrade pip

RUN pip install PyMuPDF grip qrcode xlib pyqt5 && rm -rf /root/.cache

RUN git clone --depth=1 https://github.com/manateelazycat/emacs-application-framework

RUN useradd --uid 1000  -ms /bin/bash eaf

ENV HOME=/home/eaf
ENV LANG=zh_CN.UTF-8

USER eaf

# COPY .emacs /home/eaf/


CMD ["emacs","-L","/emacs-application-framework","--eval","(require 'eaf)"]
