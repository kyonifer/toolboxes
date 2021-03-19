FROM docker.io/library/archlinux:base-devel

ENV NAME=archlinux-toolbox VERSION=base-devel
LABEL com.github.containers.toolbox="true" \
      com.github.debarshiray.toolbox="true" \
      name="$NAME" \
      version="$VERSION" \
      usage="This image is meant to be used with the toolbox command" \
      summary="Base image for creating Arch Linux toolbox containers" \
      maintainer="Kyle Kauffman <contact@kyonifer.com>"

RUN touch /etc/machine-id
COPY sudoers /etc/sudoers.d/10-toolbox
COPY extra-packages /
RUN pacman -Syu --needed --noconfirm - < extra-packages
RUN rm /extra-packages
RUN pacman -Scc --noconfirm

CMD /bin/sh
