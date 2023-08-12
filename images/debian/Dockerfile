FROM linuxserver/webtop:debian-kde

RUN echo "***** First we will update the packages *****"
RUN sudo apt update
RUN sudo apt upgrade -y
RUN echo "***** Install wget to download software *****"
RUN sudo apt install wget -y

RUN echo "***** Make a temporary directory to install software and clean it afterwards *****"

WORKDIR /config/tmp
RUN wget https://wdl1.pcfg.cache.wpscdn.com/wpsdl/wpsoffice/download/linux/11698/wps-office_11.1.0.11698.XA_amd64.deb
RUN sudo apt install ./wps-office_11.1.0.11698.XA_amd64.deb -y

WORKDIR /config/tmp/dictionaries/nl_NL
RUN wget https://github.com/OpenTaal/opentaal-hunspell/raw/master/nl.dic
RUN wget https://github.com/OpenTaal/opentaal-hunspell/raw/master/nl.aff
RUN wget https://github.com/coskun1990/opentaal-hunspell/raw/master/dict.conf
RUN sudo mkdir /opt/kingsoft/wps-office/office6/dicts/spellcheck/nl_NL
RUN sudo cp /config/tmp/dictionaries/nl_NL/nl.dic /opt/kingsoft/wps-office/office6/dicts/spellcheck/nl_NL/main.dic
RUN sudo cp /config/tmp/dictionaries/nl_NL/nl.aff /opt/kingsoft/wps-office/office6/dicts/spellcheck/nl_NL/main.aff
RUN sudo cp /config/tmp/dictionaries/nl_NL/dict.conf /opt/kingsoft/wps-office/office6/dicts/spellcheck/nl_NL/dict.conf

WORKDIR /config/tmp
RUN wget http://deb.anydesk.com/pool/main/a/anydesk/anydesk_6.2.1_amd64.deb
RUN sudo apt install ./anydesk_6.2.1_amd64.deb -y

#WORKDIR /config/Desktop
#RUN sudo sh -c "echo '[Desktop Entry]\nName=Full HD\nExec=kscreen-doctor output.VNC-0.mode.62\nType=Application\nTerminal=false' > ./fullhd.desktop"
#RUN sudo sh -c "echo '[Desktop Entry]\nName=Restore\nExec=kscreen-doctor output.VNC-0.mode.1331\nType=Application\nTerminal=false' > ./reset.desktop"

RUN echo "***** Let's clean ;-) *****"

WORKDIR /config/tmp/
RUN rm -r dictionaries
RUN rm anydesk_6.2.1_amd64.deb
RUN rm wps-office_11.1.0.11698.XA_amd64.deb

RUN echo "***** Cleaing is done :-) *****"

RUN echo "***** Everything is installed succesfully *****"