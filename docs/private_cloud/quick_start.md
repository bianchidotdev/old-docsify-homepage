Quick Start
=============

<script src="//cdn.jsdelivr.net/npm/prismjs@1/components/prism-bash.min.js"></script>

## Source Code

Clone the repo at the [michaeldbianchi/privatecloud](https://github.com/michaeldbianchi/privatecloud)


### Setup

```sh
# Run the setup script
./bin/setup
```

Update configuration and secrets in `db.env` and `.env`.

```sh
# .env
DATA_DIR=${HOME}/data          # any directory for nextcloud and plex data to be stored
BASE_DOMAIN=example.com        # your domain - required for HTTPS to work
NEXTCLOUD_SUBDOMAIN=nextcloud. # trailing . required for interpolation
ROUTER_SUBDOMAIN=router.
TRAEFIK_SUBDOMAIN=traefik.


# db.env
POSTGRES_PASSWORD=<INSERTSTRONGPASSWORDHERE>
POSTGRES_DB=nextcloud
POSTGRES_USER=nextcloud
```

## Networking
You have 2 options here, either do the full setup (described on the [networking page](private_cloud/networking.md)) which involves setting up DNS with your actual domain and port forwarding, or set up a local override, described below.

### Local DNS Override
Set up DNS overrides using `/etc/hosts` (Linux or Mac)

Usually requires `sudo` unless you are acting as root

**set_dns_overrides.sh**

[gist: set_dns_overrides.sh](https://gist.githubusercontent.com/michaeldbianchi/c9c79d37de8d125c2ac82df8a13773ff/raw/set_dns_overrides.sh ':include :type=code')

This script is also included as an executable in the source code under `./bin/set_dns_overrides.sh`

NOTE: If you are setting this up on a remote host, feel free to change `127.0.0.1` with the IP address of the server.

## Run the app

```sh
docker-compose up -d    # run app in background
docker-compose -f logs  # tail the logs

open http://cloud.example.com  # open the browser for your cloud page
```

If you are using the local DNS override, you can expect errors from the browser as well as the Traefik service saying it is unable to generate SSL certificates. This is fine and won't impede local testing.
