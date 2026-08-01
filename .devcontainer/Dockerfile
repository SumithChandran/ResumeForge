FROM mcr.microsoft.com/devcontainers/base:ubuntu-24.04

RUN apt-get update \
    && DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends \
        latexmk \
        make \
        texlive-fonts-extra \
        texlive-xetex \
    && mkdir -p /home/codespace/.config/vscode-dev-containers \
    && chown -R vscode:vscode /home/codespace \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*