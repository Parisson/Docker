FROM ubuntu:precise
MAINTAINER Thomas Fillon <thomas@parisson.com>

RUN apt-get update --fix-missing
RUN apt-get install -y python python-dev python-pip python-setuptools python-numpy python-scipy python-h5py python-matplotlib python-imaging python-simplejson python-yaml python-mutagen libhdf5-serial-dev python-tables python-gst0.10 gstreamer0.10-gnonlin gstreamer0.10-plugins-good gstreamer0.10-plugins-bad gstreamer0.10-plugins-ugly

# Add optionnal packages
RUN apt-get install vamp-examples django django-south djangorestframework django-extensions

# Add Parisson packages repository for ubuntu precise
RUN gpg --keyserver pgpkeys.mit.edu --recv-key E3298399DF14BB7C
RUN gpg -a --export E3298399DF14BB7C | sudo apt-key add - 

RUN echo "deb http://debian.parisson.com/debian/ precise main" | sudo tee -a /etc/apt/sources.list.d/parisson.list
RUN echo "deb-src http://debian.parisson.com/debian/ precise main" | sudo tee -a /etc/apt/sources.list.d/parisson.list

RUN apt-get install aubio yaafe python-aubio python-yaafe

# Update setuptools
RUN pip install -U setuptools
