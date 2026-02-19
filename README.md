sonarr, radarr, qbittorrent can be accessed by other services with a docker compose service names and port numbers, e.g
radarr:7878

All external traffic goes through the Caddy reverseproxy
mDNS service used to broadcast local FQDN's
Used https://avahi.org/ in my case

Added avahi systemd unit file as an example
https://github.com/mlx3im/jelly-stack/blob/master/avahi-alias%40.service

Aliases can be added in the following way:
systemctl --user start avahi-alias@qbit
systemctl --user start avahi-alias@jellyfin
systemctl --user start avahi-alias@sonarr
etc.

External endpoints look like this:
jellyfin.local
sonarr.local
radarr.local
etc.

