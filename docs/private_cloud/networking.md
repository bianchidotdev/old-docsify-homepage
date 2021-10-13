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

Create a(n) A record(s):

* `A   *.example.com   <public ip address>` for wildcard routing

- or -

* `A   cloud.example.com     <public ip address>`
* `A   traefik.example.com   <public ip address>`



### Dynamic DNS

Unless you are getting a static IP from your ISP or cloud provider, your public IP address will likely change on every reboot of your router.

A common solution is to use a DynamicDNS service or tool to automatically configure DNS to point at your most current public IP address. Since this will change by provider, I'll just link instructions on a handful of popular one:

* Cloudflare - [cloudflare-ddns](https://github.com/hugomd/cloudflare-ddns)
* Namecheap - [docs](https://www.namecheap.com/support/knowledgebase/article.aspx/43/11/how-do-i-set-up-a-host-for-dynamic-dns/)
* Any provider - [ddns-updater](https://github.com/qdm12/ddns-updater)

### Port Forwarding
Now that we have DNS set up, a network request to your domain should arrive at your network router. However, your router will likely just block that request unless explicitly told to route it to some backend server.

Once again, each provider is different, but in most cases you'll need to access your router's admin page (often http://192.168.1.0 or http://192.168.1.1), and set up port forwarding rules.

In order for this project to work, you'll need to route ports 80 and 443 to the server's internal IP address in your network.

* Port 80 is required for letsencrypt to validate your domain
* Port 443 is required for all other network traffic

[Find your internal IP address](https://lifehacker.com/how-to-find-your-local-and-external-ip-address-5833108)

Depending on your setup, it may also be necessary to set a static IP for your machines. This should also be available in your router config.

### Validation

Verify the DNS by making sure your public IP and DNS IP match:

Uses [dig](https://docs.digitalocean.com/products/networking/dns/resources/use-dig/)

```sh
curl icanhazip.com
#=> 93.184.216.34
dig +short example.com
#=> 93.184.216.34
```

Now try navigating to your website (ie. https://cloud.example.com).

Check the logs if something's not working:
```sh
docker-compose logs -f
```
