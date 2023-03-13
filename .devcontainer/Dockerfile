FROM mcr.microsoft.com/devcontainers/typescript-node:0-18

USER root

ENV DEBIAN_FRONTEND=noninteractive
ENV DBUS_SYSTEM_BUS_ADDRESS=unix:path=/host/run/dbus/system_bus_socket

RUN apt-get update -y --no-install-recommends \
    && apt-get install -y --no-install-recommends \
    sudo \
    build-essential \
    xz-utils \
    curl \
    ca-certificates \
    apt-utils \
    dialog \
    git \
    xauth \
    x-window-system \
    mesa-utils

RUN apt-get update -y --no-install-recommends \
    && apt-get install -y --no-install-recommends \
    libx11-xcb1 \
    libxcb-dri3-0 \
    libgbm1 \
    libxtst6 \
    libnss3 \
    libatk-bridge2.0-0 \
    libgtk-3-0 \
    libxss1 libasound2 \
    libdrm-dev \
    libgl1-mesa-glx \
    libcanberra-gtk-module libcanberra-gtk3-module \
    x11-apps

RUN apt-get update && apt-get install -yq --no-install-suggests --no-install-recommends \
    xinit \
    xdg-utils \
    libgdk-pixbuf2.0-0 \
    xserver-xorg-video-dummy \
    xserver-xorg-legacy \
    x11-xserver-utils \
    fonts-liberation \
    fonts-roboto \
    fonts-symbola

RUN apt-get autoremove -y \
    && apt-get clean -y \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

RUN /etc/init.d/dbus start

USER $USERNAME