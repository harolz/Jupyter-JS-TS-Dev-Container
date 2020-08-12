#-------------------------------------------------------------------------------------------------------------
# Copyright (c) Microsoft Corporation. All rights reserved.
# Licensed under the MIT License. See https://go.microsoft.com/fwlink/?linkid=2090316 for license information.
#-------------------------------------------------------------------------------------------------------------

# To fully customize the contents of this image, use the following Dockerfile instead:
# https://github.com/microsoft/vscode-dev-containers/tree/v0.128.0/containers/typescript-node-14/.devcontainer/Dockerfile
FROM mcr.microsoft.com/vscode/devcontainers/typescript-node:0-14

# ** [Optional] Uncomment this section to install additional packages. **
#
# RUN apt-get update \
#     && export DEBIAN_FRONTEND=noninteractive \
#     && apt-get -y install --no-install-recommends <your-package-list-here>

# installing t
RUN apt-get update && \
    apt-get install -y apt-utils && \
    apt-get -y dist-upgrade && \
    apt-get -y install --no-install-recommends python-dev python3-dev python-pip python3-pip && \
    rm -rf /var/lib/apt/lists/*

RUN apt-get update && sudo apt-get upgrade && apt-get install -y python-setuptools python3-setuptools

RUN python3 -m pip install --upgrade pip && \
    python2 -m pip install --upgrade pip

RUN python3 -m pip install jupyterlab && \
    jupyter serverextension enable --py jupyterlab && \
    python2 -m pip install ipykernel && \
    python2 -m ipykernel install --user

RUN npm --unsafe-perm i -g ijavascript && \
    ijsinstall --install=global

ENV HOME /workspaces
ENV SERVER_PORT 8888

EXPOSE $SERVER_PORT
# CMD jupyter lab --ip=* --port=$SERVER_PORT --no-browser --notebook-dir=$HOME --allow-root --NotebookApp.token='' --NotebookApp.password=''

