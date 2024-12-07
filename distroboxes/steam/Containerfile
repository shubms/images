FROM ghcr.io/ublue-os/arch-distrobox:latest

LABEL com.github.containers.toolbox="true" \
    name="steam-container"

RUN pacman -Syu --noconfirm \
    glibc-locales \
    lib32-vulkan-mesa-layers \
    lib32-vulkan-radeon \
    lib32-mangohud \
    pipewire-alsa \
    pipewire-pulse \
    steam \
    ttf-liberation \
    xdg-desktop-portal-gnome && \
    pacman -Sc --noconfirm

VOLUME /steam /var/home
