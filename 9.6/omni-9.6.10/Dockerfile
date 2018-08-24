FROM postgres:9.6.10

# install git-lfs
RUN set -x \
	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates curl ssh wget \
	&& curl -s https://packagecloud.io/install/repositories/github/git-lfs/script.deb.sh | bash \
	&& apt-get install -y --no-install-recommends git-lfs postgresql-plperl-9.6 \
	&& rm -rf /var/lib/apt/lists/*

# install jq 1.5
RUN curl -Lo /usr/local/bin/jq https://github.com/stedolan/jq/releases/download/jq-1.5/jq-linux64 \
	&& chmod +x /usr/local/bin/jq

# install dockerize
ENV DOCKERIZE_VERSION v0.5.0
RUN wget https://github.com/jwilder/dockerize/releases/download/$DOCKERIZE_VERSION/dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && tar -C /usr/local/bin -xzvf dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && rm dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz