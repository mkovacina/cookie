# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.183.0/containers/ubuntu/.devcontainer/base.Dockerfile

# [Choice] Ubuntu version: bionic, focal
ARG VARIANT="focal"
FROM mcr.microsoft.com/vscode/devcontainers/base:0-${VARIANT}

# [Optional] Uncomment this section to install additional OS packages.
RUN apt-get update 
RUN export DEBIAN_FRONTEND=noninteractive 
RUN apt-get -y install --no-install-recommends ruby-full build-essential zlib1g-dev

USER vscode
ENV HOME /home/vscode
RUN echo '# Install Ruby Gems to ~/gems' >> /home/vscode/.bashrc
RUN echo 'export GEM_HOME="$HOME/gems"' >> /home/vscode/.bashrc
RUN echo 'export PATH="$HOME/gems/bin:$PATH"' >> /home/vscode/.bashrc

ENV GEM_HOME="/home/vscode/gems"
RUN echo $HOME

 RUN gem install jekyll bundler

## TODO: squash the layers
## TODO: dump the APT cache