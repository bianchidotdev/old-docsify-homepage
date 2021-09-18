Home Cloud Setup (with NextCloud, Plex, and Traefik)
=============

## What this is
A simple, repeatable setup for a private cloud anyone can set up and start down their journey towards [privacy](https://www.reddit.com/r/privacy/wiki/index).

This setup goes through installation of the following:
- [NextCloud](https://nextcloud.com/)
- [Plex](https://www.plex.tv/)
- Auto HTTPS via [Traefik](https://traefik.io/)
- Simple Networking

## Source Code
All code is hosted on [GitHub](https://github.com/michaeldbianchi/privatecloud)

## Why do this
In the last few years, I've become more aware and upset at the amount of data I've published to the public internet and to companies that should not be trusted to store our data securely.

This home setup is an effort to degoogle and reduce my reliance on "free" services that profit from my data.

In order for this to be more commonly adopted, the barrier of entry needs to decrease such that just about anyone could set up a secure and private cloud.

I am writing this guide so that others starting to see the value of a self-hosted cloud can easily stand up their own.

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

If you just want to test this out in an ephemeral environment, I included a `Vagrantfile` in the source code repo.

### Vagrant Instructions

```bash
vagrant plugin install vagrant-docker-compose
vagrant up
vagrant ssh

cd privatecloud
```

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
