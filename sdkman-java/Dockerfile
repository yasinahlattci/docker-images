FROM ubuntu:20.04

RUN apt-get update
ARG JAVA_VERSION=17.0.5-amzn
RUN rm /bin/sh && ln -s /bin/bash /bin/sh
RUN apt-get -qq -y install curl wget unzip zip

RUN curl -s "https://get.sdkman.io" | bash
RUN source "$HOME/.sdkman/bin/sdkman-init.sh" && sdk install java $JAVA_VERSION

ENTRYPOINT ["/bin/bash"]
