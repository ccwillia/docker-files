FROM alpine:latest

RUN apk update && apk --no-cache add ca-certificates git wget

WORKDIR /opt/hub
ENV PATH /opt/hub/bin:$PATH

RUN export PATH=$PATH

ENV GITHUB_HUB_VERSION 2.3.0-pre10

RUN set -ex; \
	\
	wget -O hub.tgz "https://github.com/github/hub/releases/download/v${GITHUB_HUB_VERSION}/hub-linux-386-${GITHUB_HUB_VERSION}.tgz"; \
	tar -xvzf hub.tgz --strip-components=1; \
	rm -v hub.tgz; \
	\
	hub --version

CMD ["hub"]
