FROM ghcr.io/archlinux/archlinux:multilib-devel

LABEL com.github.containers.toolbox="true" \
    name="steam-container"

RUN pacman -Syu --noconfirm \
    # Distrobox default packages
    bash-completion bc glibc-locales inetutils lsof man-db man-pages mtr nss-mdns openssh pigz rsync tcpdump time traceroute tree unzip vte-common vulkan-intel vulkan-radeon wget words xorg-xauth zip \
    # Steam and graphics
    lib32-vulkan-mesa-layers lib32-vulkan-radeon lib32-mangohud pipewire-alsa pipewire-pulse steam ttf-liberation xdg-desktop-portal-gnome && \
    pacman -Sc --noconfirm

VOLUME /steam /var/home
