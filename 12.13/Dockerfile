# vim:set ft=dockerfile:

# Do not edit individual Dockerfiles manually. Instead, please make changes to the Dockerfile.template, which will be used by the build script to generate Dockerfiles.

FROM cimg/base:2022.04

LABEL maintainer="Community & Partner Engineering Team <community-partner@circleci.com>"

ENV NODE_VERSION 12.13.1
ENV NVM_DIR /home/circleci/.nvm

RUN curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash && \
	echo 'export NVM_DIR="$HOME/.nvm"' >> ~/.bashrc && \
	echo '[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" --no-use' >> ~/.bashrc && \
	echo 'nvm use default' >> ~/.bashrc && \
 	echo 'sudo ln -sf $NVM_DIR/versions/node/$(nvm version)/bin/node /usr/local/bin/node' >> ~/.bashrc && \
	echo 'sudo ln -sf $NVM_DIR/versions/node/$(nvm version)/bin/npm /usr/local/bin/npm' >> ~/.bashrc

ENV YARN_VERSION 1.22.18
RUN curl -L -o yarn.tar.gz "https://yarnpkg.com/downloads/${YARN_VERSION}/yarn-v${YARN_VERSION}.tar.gz" && \
	sudo tar -xzf yarn.tar.gz -C /opt/ && \
	rm yarn.tar.gz && \
	sudo ln -s /opt/yarn-v${YARN_VERSION}/bin/yarn /usr/local/bin/yarn && \
	sudo ln -s /opt/yarn-v${YARN_VERSION}/bin/yarnpkg /usr/local/bin/yarnpkg
