FROM ubuntu:precise
MAINTAINER Thomas Fillon <thomas@parisson.com>

RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y \
    python \ 
    python-dev \
    python-pip \ 
    python-setuptools \
    python-numpy \
    python-scipy \
    python-h5py \
    python-matplotlib \ 
    python-imaging \
    python-simplejson \ 
    python-yaml \
    python-mutagen \
    libhdf5-serial-dev \
    python-tables \
    python-gst0.10 \
    gstreamer0.10-gnonlin \
    gstreamer0.10-plugins-good \
    gstreamer0.10-plugins-bad \
    gstreamer0.10-plugins-ugly \
    gstreamer0.10-alsa

# Update setuptools
RUN pip install -U setuptools
