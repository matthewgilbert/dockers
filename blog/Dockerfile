## Dockerfile for generating blog

FROM debian:8.4

MAINTAINER Matthew Gilbert <matthew.gilbert12@gmail.com>

RUN apt-get update && apt-get install -y \
    wget git bzip2 make vim

RUN mkdir -p /home/matthew/Projects

RUN echo 'export PATH=/opt/conda/bin:$PATH' > /etc/profile.d/conda.sh && \
    wget --quiet https://repo.continuum.io/archive/Anaconda2-4.0.0-Linux-x86_64.sh && \
    /bin/bash /Anaconda2-4.0.0-Linux-x86_64.sh -b -p /opt/conda && \
    rm /Anaconda2-4.0.0-Linux-x86_64.sh

ENV PATH /opt/conda/bin:$PATH

RUN conda install markdown==2.6.6
RUN pip install pelican==3.6.3

RUN git clone https://github.com/matthewgilbert/blog.git /home/matthew/Projects/blog && \
    cd /home/matthew/Projects/blog && git submodule init && git submodule update
