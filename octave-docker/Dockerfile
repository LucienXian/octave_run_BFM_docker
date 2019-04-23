FROM ubuntu:16.04
MAINTAINER ome-devel@lists.openmicroscopy.org.uk

ARG UBUNTU_MIRROR

ENV DEBIAN_FRONTEND noninteractive

RUN /bin/bash -c 'if [[ -n ${UBUNTU_MIRROR} ]]; then sed -i 's#http://archive.ubuntu.com#${UBUNTU_MIRROR}#g' /etc/apt/sources.list; fi'

RUN apt-get update \
    && apt-get install less \
    && rm -rf /var/lib/apt/lists/* \
    && apt-get clean
ADD install.sh install.sh
RUN sh ./install.sh && rm install.sh
RUN useradd -ms /bin/bash octave
ADD *.m /home/octave/
RUN chown -R octave:octave /home/octave/

USER octave
WORKDIR /home/octave

VOLUME ["/source"]
ENTRYPOINT ["octave"]
