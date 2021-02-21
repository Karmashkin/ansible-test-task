FROM alpine:3.13
MAINTAINER Karmashkin <vlad@zolotous.com>

RUN apk add --no-cache ansible \
                       ansible-lint \
                       ansible-base-doc \
                       bash \
                       rsync \
                       libressl \
                       openssl \
                       openssh-client \
                       tzdata

WORKDIR /etc/ansible

CMD ["ansible", "-h"]

