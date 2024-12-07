FROM ghcr.io/ublue-os/ubuntu-toolbox:latest

LABEL com.github.containers.toolbox="true" \
    name="spotify-container"

RUN curl -sS https://download.spotify.com/debian/pubkey_6224F9941A8AA6D1.gpg | \
    gpg --dearmor --yes -o /etc/apt/trusted.gpg.d/spotify.gpg && \
    echo "deb http://repository.spotify.com stable non-free" | \
    tee /etc/apt/sources.list.d/spotify.list && \
    ln -sf /usr/share/spotify/spotify.desktop /usr/share/applications/spotify.desktop && \
    ln -sf /usr/share/spotify/icons/spotify_icon.ico /usr/share/icons/spotify.ico
RUN DEBIAN_FRONTEND=noninteractive apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get -y upgrade && \
    DEBIAN_FRONTEND=noninteractive apt-get -y install \
    pipewire spotify-client && \
    rm -rd /var/lib/apt/lists/*

VOLUME /var/home
