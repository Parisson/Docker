FROM debian:wheezy
MAINTAINER Thomas Fillon <thomas@parisson.com>

RUN apt-get update && apt-get install -y \
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

# Add optionnal packages (missing python-djangorestframework and python-django-extensions)
RUN apt-get install -y \
    vamp-examples \
    python-django \
    python-django-south
 

# Add Parisson packages repository for debian wheezy and install Aubio and Yaafe
RUN gpg --keyserver pgpkeys.mit.edu --recv-key E3298399DF14BB7C && \
    gpg -a --export E3298399DF14BB7C | apt-key add - && \
    echo "deb http://http.debian.net/debian/ wheezy-backports main" | \
    tee -a /etc/apt/sources.list.d/parisson.list && \
    echo "deb-src http://http.debian.net/debian/ wheezy-backports main" | \
    tee -a /etc/apt/sources.list.d/parisson.list && \
    echo "deb http://debian.parisson.com/debian/ wheezy main" | \
    tee -a /etc/apt/sources.list.d/parisson.list && \
    echo "deb-src http://debian.parisson.com/debian/ wheezy main" | \
    tee -a /etc/apt/sources.list.d/parisson.list && \
    apt-get update && \
    apt-get install -t wheezy-backports -y python-aubio python-yaafe

