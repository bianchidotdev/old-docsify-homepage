Networking
=============

## Setup

If you want to just set up this project locally, follow the process in the [Quickstart](private_cloud/quick_start.md).

This will walk through the following steps:
1. DNS Setup
1. Port-forwarding

### DNS Setup

Set up DNS to point to your server/computer.

This is required for at least the subdomains you specified in the `.env` file. Optionally, you can add a wildcard (*) resolution for your domain.

Implementation will vary by provider, but you will just need to add an A record pointing to your public IP address.

Find your public IP address

```sh
curl icanhazip.org
```
