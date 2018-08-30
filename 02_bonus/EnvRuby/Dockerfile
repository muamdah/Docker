FROM ubuntu

RUN apt-get update -y && apt-get upgrade -y \
	&& apt-get install -y sudo \
	build-essential zlib1g-dev libyaml-dev libssl-dev libgdbm-dev libre2-dev \
	libreadline-dev libncurses5-dev libffi-dev curl openssh-server checkinstall \
	libxml2-dev libxslt-dev libcurl4-openssl-dev libicu-dev logrotate rsync \
	python-docutils pkg-config cmake vim
RUN apt-get remove -y ruby1.8 \
	&& mkdir /tmp/ruby && cd /tmp/ruby \
	&& curl --remote-name --progress https://cache.ruby-lang.org/pub/ruby/2.4/ruby-2.4.3.tar.gz \
	&& tar xvfz ruby-2.4.3.tar.gz \
	&& cd ruby-2.4.3 \
	&& ./configure --disable-install-rdoc \
	&& make \
	&& make install \
	&& gem install bundler --no-ri --no-rdoc

CMD /bin/bash
