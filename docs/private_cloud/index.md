Home Cloud Setup (with NextCloud, Plex, and Traefik)
=============

## What this is
A simple, repeatable setup for a private cloud able to be run just about any system that can run Docker/Podman.

This setup goes through installation of the following:
- [NextCloud]()
- [Plex Server]()
- Auto HTTPS via [Traefik]()
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

### Mac Install Instructions

```bash
brew install --formula docker  # docker cli
brew install --cask docker  # docker desktop
```