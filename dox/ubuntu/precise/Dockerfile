FROM ubuntu:precise
MAINTAINER Thomas Fillon <thomas@parisson.com>

# Install python-software-properties to get 'add-apt-repository' and 'lsb_release' utilities
RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y python-software-properties

# Install TimeSide dependencies
RUN add-apt-repository -y ppa:donk/gstreamer && \
    apt-get update && \
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

# Update setuptools and install virutalenv
RUN pip install -U setuptools && \
    pip install -U virtualenv

# Add optionnal packages (missing python-djangorestframework not available in precise)
RUN apt-get install -y \
    vamp-examples \
    python-django \
    python-django-south \
    python-django-extensions

# Add Parisson packages repository for ubuntu precise and install Aubio, Yaafe
RUN gpg --keyserver pgpkeys.mit.edu --recv-key E3298399DF14BB7C && \
    gpg -a --export E3298399DF14BB7C | apt-key add - && \
    echo "deb http://debian.parisson.com/debian/ precise main" | \
    tee -a /etc/apt/sources.list.d/parisson.list && \
    echo "deb-src http://debian.parisson.com/debian/ precise main" | \
    tee -a /etc/apt/sources.list.d/parisson.list && \
    apt-get update && \
    apt-get install -y python-aubio python-yaafe


