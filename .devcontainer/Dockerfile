FROM mcr.microsoft.com/vscode/devcontainers/python:3.11

# Instala Google Chrome
RUN apt-get update && \
    apt-get install -y wget gnupg && \
    wget -q -O - https://dl.google.com/linux/linux_signing_key.pub | apt-key add - && \
    sh -c 'echo "deb [arch=amd64] http://dl.google.com/linux/chrome/deb/ stable main" > /etc/apt/sources.list.d/google-chrome.list' && \
    apt-get update && \
    apt-get install -y google-chrome-stable

# Avoid prompts from apt
ENV DEBIAN_FRONTEND=noninteractive

#COPY .requirements.txt /tmp/
COPY .devcontainer/requirements.txt /tmp/

# Instala Git
RUN apt-get update && \
#    apt-get upgrade &&\
    apt-get install -y git && \
    rm -rf /var/lib/apt/lists/*

# Configura las credenciales de Git
#RUN git config --global user.name "$GIT_USER_NAME" && \
#    git config --global user.email "$GIT_USER_EMAIL"

# Actualiza pip
RUN pip3 install --upgrade pip

RUN set -ex; \
    pip3 --no-cache-dir install --requirement /tmp/requirements.txt
