Networking
=============

## Coming Soon
Set up DNS to point to your server/computer.

This is required for at least the subdomains you specified in the `.env` file. Optionally, you can add a wildcard (*) resolution for your domain.

Implementation will vary by provider, but you will just need to add an A record pointing to your public IP address.

Find your public IP address

```sh
curl icanhazip.org
```

NOTE: Your public IP will likely change, see the [networking page](private_cloud/networking.md) for details of how to set up Dynamic DNS.