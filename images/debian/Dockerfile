FROM linuxserver/webtop:debian-kde

RUN echo "***** First we will update the packages *****"
RUN sudo apt update
RUN sudo apt upgrade -y
RUN echo "***** Install wget to download software *****"
RUN sudo apt install wget -y
RUN echo "***** Make a temporary directory to install software and clean it afterwards *****"
RUN mkdir /config/tmp
RUN mkdir /config/tmp/dictionaries
RUN mkdir /config/tmp/dictionaries/nl_NL
RUN cd /config/tmp
RUN wget https://wdl1.pcfg.cache.wpscdn.com/wpsdl/wpsoffice/download/linux/11698/wps-office_11.1.0.11698.XA_amd64.deb
RUN sudo apt install ./wps-office_11.1.0.11698.XA_amd64.deb -y
RUN cd /config/tmp/dictionaries/nl_NL
RUN wget https://github.com/OpenTaal/opentaal-hunspell/raw/master/nl.dic
RUN wget https://github.com/OpenTaal/opentaal-hunspell/raw/master/nl.aff
RUN wget https://github.com/coskun1990/opentaal-hunspell/raw/master/dict.conf
RUN sudo mkdir /opt/kingsoft/wps-office/office6/dicts/spellcheck/nl_NL
RUN sudo cp /config/tmp/dictionaries/nl_NL/nl.dic /opt/kingsoft/wps-office/office6/dicts/spellcheck/nl_NL/main.dic
RUN sudo cp /config/tmp/dictionaries/nl_NL/nl.aff /opt/kingsoft/wps-office/office6/dicts/spellcheck/nl_NL/main.aff
RUN sudo cp /config/tmp/dictionaries/nl_NL/dict.conf /opt/kingsoft/wps-office/office6/dicts/spellcheck/nl_NL/dict.conf

RUN echo "***** Everything is installed succesfully *****"
