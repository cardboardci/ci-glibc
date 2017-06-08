FROM jrbeverly/baseimage:alpine-3.5
MAINTAINER jrbeverly

#
# Build Arguments
#
ARG ALPINE_GLIBC_BASE_URL
ARG ALPINE_GLIBC_KEY
ARG ALPINE_GLIBC_PACKAGE_VERSION

#
# Provision
#

COPY provision/install.sh /tmp/install.sh
RUN sh /tmp/install.sh && rm -f /tmp/install.sh

# 
# Options
# 
WORKDIR /media
ENTRYPOINT []
CMD []

#
# User
#
ARG USER
USER $USER

#
# Metadata Arguments
#
ARG BUILD_DATE
ARG VERSION
ARG VCS_REF

#
# Metadata
#
LABEL \
    maintainer="jrbeverly" \
    \
    org.label-schema.name="glibc" \
    org.label-schema.summary="An alpine image with glibc to act as a glibc base." \
    org.label-schema.description="An alpine image with glibc to act as a glibc base." \
    org.label-schema.maintainer="jrbeverly" \
    org.label-schema.build-date=$BUILD_DATE \
    org.label-schema.version=$VERSION \
    org.label-schema.url="https://github.com/sgerrand/alpine-pkg-glibc" \
    org.label-schema.license="MIT" \
    org.label-schema.vcs-type="Git" \
    org.label-schema.vcs-ref=$VCS_REF \
    org.label-schema.vcs-url="https://gitlab.com/jrbeverly-docker/docker-glibc" \
    org.label-schema.docker.cmd="docker run -it -v $(pwd):/media/ jrbeverly/glibc:baseimage sh" \
    \
    io.jrbeverly.project="glibc" \
    io.jrbeverly.summary="A docker image with glibc installed, running as the $USER user." \
    io.jrbeverly.glibc.meta.BUILD_DATE="The Date/Time the image was built." \
    io.jrbeverly.glibc.meta.VERSION="Release identifier for the contents of the image." \
    io.jrbeverly.glibc.meta.VCS_REF="Identifier for the version of the source code from which this image was built." \
    io.jrbeverly.glibc.args.USER="Sets the [user](http://www.linfo.org/uid.html) to use when running the image." \
    io.jrbeverly.glibc.args.ALPINE_GLIBC_BASE_URL="The base url to download the alpine apk." \
    io.jrbeverly.glibc.args.ALPINE_GLIBC_KEY="The URL to download the software signature key." \
    io.jrbeverly.glibc.args.ALPINE_GLIBC_PACKAGE_VERSION="The apk version to download." \
    io.jrbeverly.glibc.volume.media="/media/|The default working directory of the image."