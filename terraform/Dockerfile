FROM alpine:3.16.3

ARG TERRAFORM_VERSION=1.3.4
ARG TERRAGRUNT_VERSION=0.40.2

RUN apk add git bash curl make

RUN git clone --depth=1 https://github.com/tfutils/tfenv.git ~/.tfenv && \
    echo 'export PATH="$HOME/.tfenv/bin:$PATH"' >> ~/.bashrc && \
    git clone https://github.com/cunymatthieu/tgenv.git ~/.tgenv && \
    echo 'export PATH="$HOME/.tgenv/bin:$PATH"' >> ~/.bashrc

RUN source ~/.bashrc && tfenv install $TERRAFORM_VERSION && tfenv use $TERRAFORM_VERSION && \
    tgenv install $TERRAGRUNT_VERSION && tgenv use $TERRAGRUNT_VERSION

ENTRYPOINT ["/bin/bash"]