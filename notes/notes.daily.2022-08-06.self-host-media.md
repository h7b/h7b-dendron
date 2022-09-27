---
id: c1ogxa7radpi0v31w6iq7w1
title: Self-host media server
desc: Self-host media server
updated: 1661177189991
created: 1659815661635
tags: cat.tut
---
# Self-host a media server

ref: [r/selfhosted](https://www.reddit.com/r/selfhosted/comments/whj6k2/selfhost_complete_media_stack/)

The [tutorial](https://medium.com/linux-shots/self-host-media-stack-jellyfin-radarr-sonarr-jackett-transmission-3e6a0adf716e) helps to self-host your own media streamer and manager on your home server. Deploy complete media stack (jellyfin + radarr + sonarr + jackett + transmission).

![self-host-media-stack](https://miro.medium.com/max/1400/1*SfpjRTwK0vaxG3aTMRamCA.png){max-width: 300px, display: block, margin: 0 auto}

- [Jellyfin](https://jellyfin.org/) is used to manage and stream media
- [Radarr](https://radarr.video/) is used to automatically download movies via Usenet and BitTorrent
- [Sonarr](https://sonarr.tv/) is used to automatically download TV Shows via Usenet and BitTorrent
- [Jackett](https://github.com/Jackett/Jackett) is a proxy server used for parsing results requested by any application from tracker sites
- [Transmission](https://transmissionbt.com/) is a BitTorrent client used for downloading, seeding and peering on torrent network
    - Alternative: [qBittorrent ](https://github.com/qbittorrent/qBittorrent)

## Related

- [r/selfhosted | A Modern Homeserver Guide - from A to Z - Hardware - domain config - docker - filesystem - backups - maintenance and more](https://www.reddit.com/r/selfhosted/comments/vtdzlc/a_modern_homeserver_guide_from_a_to_z_hardware/)
    - a detailed guide from A to Z, the guide also contains the full media stack with recommendations around VPN service, which image to use to auto update VPN port forwarding
- [Awesome Open Source | Calloboration with the IBRACORP channel on Sonarr, Jackett, QBittorrent, in Portainer and Docker](https://www.youtube.com/watch?v=Cth-bsLAa_M)
    - video walked you through the setup of home media server. Radarr, Sonarr, Jackett and qBitTorrent
- [IBRACORP | TRaSH Guides: Atomic-Moves, Hardlinks & Media Automation - Why Use](https://www.youtube.com/watch?v=AMcHsQJ7My0)
    - video walked you through the setup of home media server. Sonarr, Radarr, Lidarr, Jackett, qBitTorrent, Plex 