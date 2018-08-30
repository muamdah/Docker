FROM ubuntu

RUN apt-get update -y && apt-get upgrade -y && apt-get install -y sudo \
	&& sudo apt-get install -y curl vim build-essential zlib1g-dev libyaml-dev \
	libssl-dev libgdbm-dev libre2-dev libreadline-dev libncurses5-dev \
	libffi-dev curl openssh-server checkinstall libxml2-dev libxslt-dev \
	libcurl4-openssl-dev libicu-dev logrotate rsync python-docutils pkg-config cmake

RUN rm -rf /usr/local/go \
	&& cd /tmp && curl --remote-name --progress https://storage.googleapis.com/golang/go1.8.3.linux-amd64.tar.gz \
	&& echo '1862f4c3d3907e59b04a757cfda0ea7aa9ef39274af99a784f5be843c80c6772  go1.8.3.linux-amd64.tar.gz' | shasum -a256 -c - \
	&& tar -C /usr/local -xzf go1.8.3.linux-amd64.tar.gz \
	&& ln -sf /usr/local/go/bin/go /usr/local/bin/ \
	&& ln -sf /usr/local/go/bin/godoc /usr/local/bin/ \
	&& ln -sf /usr/local/go/bin/gofmt /usr/local/bin/ \
	&& rm go1.8.3.linux-amd64.tar.gz

CMD /bin/bash
