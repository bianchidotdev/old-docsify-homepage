Software
=============

If you are already on board with this setup (Nextcloud, Traefik, and Plex), please continue to the next page for detailed install instructions.

## Why this setup?

All software included here is self-hosted and FOSS (Free Open-Source Software). 

I won't rewrite what [others have done better](https://www.reddit.com/r/privacy/wiki/why_opensource), but simply, self-hosted open-source software is as close as we can get to having assurances that our data is safe and secure.

### Nextcloud

I wanted a software solution to handle file syncing and uploads for both myself and my close friends and family.

There aren't that many mature OSS solutions that offer user management and a reasonable interface, so Nextcloud won out with those simple features.

**Alternatives**
* OwnCloud - replaced by Nextcloud
* SyncThing - Syncs files across 2 systems, does not handle multi-user accounts
* SeaFile - similar to Nextcloud, maybe a solid alternative

### Plex

Plex is probably the most popular open-source media server out there.

I wanted to have something that provided a solid user interface for photos and video and Plex was very straightforward to setup.

**Deficiencies**
* Requires a Plex user account

### Traefik

Traefik is a cloud-native network router that provides a lot of niceties above something older-school like NGINX.

**Benefits:**
* Auto-tls via [Let's Encrypt](https://letsencrypt.org/)
* Dynamic routing through [docker labels](https://doc.traefik.io/traefik/providers/docker/)
