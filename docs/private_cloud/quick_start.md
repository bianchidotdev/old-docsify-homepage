Quick Start
=============

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
Set up DNS to point to your server/computer.

This is required for at least the subdomains you specified in the `.env` file. Optionally, you can add a wildcard (*) resolution for your domain.

Implementation will vary by provider, but you will just need to add an A record pointing to your public IP address.

Find your public IP address

```sh
curl icanhazip.org
```

NOTE: Your public IP will likely change, see the [networking page](private_cloud/networking.md) for details of how to set up Dynamic DNS.

## Run the app

```sh
docker-compose up -d    # run app in background
docker-compose -f logs  # tail the logs
```
