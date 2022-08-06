FROM postgres:14.3

RUN localedef -i vi_VN -c -f UTF-8 -A /usr/share/locale/locale.alias vi_VN.UTF-8

ENV LANG vi_VN.utf8

EXPOSE 5432