FROM debian

RUN apt-get update -y && apt-get upgrade -y && apt-get install -y sudo \
	&& apt-get install -y curl vim git build-essential zlib1g-dev libyaml-dev libssl-dev libgdbm-dev libre2-dev \
	libreadline-dev libncurses5-dev libffi-dev curl openssh-server checkinstall \
	libxml2-dev libxslt-dev libcurl4-openssl-dev libicu-dev logrotate rsync \
	python-docutils pkg-config cmake

RUN curl --location https://deb.nodesource.com/setup_8.x | sudo bash - \
	&& sudo apt-get install -y nodejs \
	&& curl --silent --show-error https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add - \
	&& echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list \
	&& sudo apt-get update -y \
	&& sudo apt-get install -y yarn

CMD /bin/bash
