FROM docker.io/library/debian:latest

LABEL com.github.containers.toolbox="true" \
    name="spotify-container"

ARG DEBIAN_FRONTEND=noninteractive

RUN curl -sS https://download.spotify.com/debian/pubkey_6224F9941A8AA6D1.gpg | \
    gpg --dearmor --yes -o /etc/apt/trusted.gpg.d/spotify.gpg && \
    echo "deb http://repository.spotify.com stable non-free" | \
    tee /etc/apt/sources.list.d/spotify.list && \
    ln -sf /usr/share/spotify/spotify.desktop /usr/share/applications/spotify.desktop && \
    ln -sf /usr/share/spotify/icons/spotify_icon.ico /usr/share/icons/spotify.ico

RUN apt-get update && \
    apt-get -y upgrade && \
    apt-get -y install \
    # Distrobox default packages
    avahi-daemon bash-completion bc bzip2 ca-certificates curl deborphan dialog gettext-base gnupg2 iproute2 iputils-ping keyutils krb5-locales less libatm1 libdpkg-perl libegl1-mesa libfile-fcntllock-perl libgail-common libgdk-pixbuf2.0-bin libgl1-mesa-glx libglib2.0-data libgpm2 libgtk2.0-bin libldap-common libnss-mdns libnss-myhostname libpam-cap librsvg2-common libsasl2-modules libvte-2.91-common libvte-common locales lsof man-db manpages mesa-vulkan-drivers mtr netbase openssh-client pigz procps psmisc publicsuffix rsync sudo tcpdump time traceroute tree unzip wget xauth xdg-user-dirs xz-utils zip \
    # Spotify and audio
    pipewire spotify-client && \
    rm -rd /var/lib/apt/lists/*

VOLUME /var/home