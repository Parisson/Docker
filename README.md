Docker
======

Collection of Docker files for Parisson

`Dox` directory contains Dockerfiles for testing TimeSide in different debian-based OS.

Docker images are automatically build and available in the Parisson repository on DockerHub.

'Minimal' images contains only the basic system packages for running TimeSide without optionnal requirements (Django, Aubio, Vamp and Yaafe libraries) 

- parisson/docker:dox_debian_jessie_mini
- parisson/docker:dox_debian_wheezy_mini
- parisson/docker:dox_ubuntu_precise_mini
- parisson/docker:dox_ubuntu_trusty_mini

'Full' images contains the same basic system packages and the optionnal ones: python-django (and some Django applications), Vamp and the Aubio and Yaafe (from Parisson debian and ubuntu repositories)

- parisson/docker:dox_debian_jessie
- parisson/docker:dox_debian_wheezy
- parisson/docker:dox_ubuntu_precise
- parisson/docker:dox_ubuntu_trusty











