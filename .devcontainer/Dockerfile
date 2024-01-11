FROM library/python:3.11-bookworm

ARG USER=vscode
ARG DEBIAN_FRONTEND=noninteractive
RUN apt update \
    && apt install -y --no-install-recommends sudo \
    && apt autoremove -y \
    && rm -rf /var/lib/apt/lists/* \
    && useradd -m -s /usr/bin/bash ${USER} \
    && echo "${USER} ALL=(ALL) NOPASSWD: ALL" >/etc/sudoers.d/${USER} \
    && chmod 0440 /etc/sudoers.d/${USER} \
    && pip install --upgrade pip

# pip3 freeze > requirements.txt
# pip3 install -r requirements.txt

# https://github.com/swar/nba_api