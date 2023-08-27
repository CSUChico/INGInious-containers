# DOCKER-VERSION 1.1.0

# Inherit from the base container, which have all the needed script to launch tasks
ARG   VERSION=latest
FROM  ingi/inginious-c-base:${VERSION}
LABEL org.inginious.grading.name="gcc11"

# Install GCC Toolset 11
RUN     dnf install -y gcc-toolset-11 && dnf clean all
RUN     dnf install -y git && dnf clean all

# Make GCC-11 default compiler
ENV    PATH=/opt/rh/gcc-toolset-11/root/usr/bin${PATH:+:${PATH}}
ENV    MANPATH=/opt/rh/gcc-toolset-11/root/usr/share/man:${MANPATH}
ENV    INFOPATH=/opt/rh/gcc-toolset-11/root/usr/share/info${INFOPATH:+:${INFOPATH}}
ENV    PCP_DIR=/opt/rh/gcc-toolset-11/root
ENV    LD_LIBRARY_PATH=/opt/rh/gcc-toolset-11/root/usr/lib64:/opt/rh/gcc-toolset-11/root/usr/lib:/opt/rh/gcc-toolset-11/root/usr/lib64/dyninst:/opt/rh/gcc-toolset-11/root/usr/lib/dyninst:/opt/rh/gcc-toolset-11/root/usr/lib64:/opt/rh/gcc-toolset-11/root/usr/lib${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}
ENV    PKG_CONFIG_PATH=/opt/rh/gcc-toolset-11/root/usr/lib64/pkgconfig${PKG_CONFIG_PATH:+:${PKG_CONFIG_PATH}}

# Install Devtools

RUN yum group install -y "Development Tools"

# Install VIM/VIMDIFF

RUN yum install -y vim-enhanced