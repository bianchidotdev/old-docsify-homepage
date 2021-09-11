Home Cloud Setup (with NextCloud, Plex, and Traefik)
=============

## What this is
A simple, repeatable setup for a private cloud anyone can set up and start down their journey towards privacy.

This setup goes through installation of the following:
- [NextCloud](https://nextcloud.com/)
- [Plex](https://www.plex.tv/)
- Auto HTTPS via [Traefik](https://traefik.io/)
- Simple Networking

## Prereqs
Hardware:
- 1 system
  - Raspberry Pi
  - Old desktop or laptop
  - Rackmount server
  - Cloud instances
  - VM on any of the above

Software (on your development machine):
- [`docker`](https://tbd)
- [`docker-compose`]() (Not needed if using a version of docker that natively includes compose - Docker CE v??? or higher)

Domain Registration
- One domain that you can control DNS with (I use Cloudflare)

### Mac Install Instructions

```bash
brew install --formula docker  # docker cli
brew install --cask docker  # docker desktop
```

### Linux Install Instructions (Debian Based)

```bash
sudo apt-get install docker
sudo apt-get install docker-ce
sudo apt-get install docker-compose
```