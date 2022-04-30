# About

This repo contains all files needed to spin up a Traefik container acting as reverse proxy as well as an Authentik container
providing further security for other hosted services.
Using these two together allows to reverse proxy services from other Docker container by putting labels on those container. These labels will
be picked up and handled by Traefik.

# References

Authelia - https://www.authelia.com
Traefik - https://traefik.io

# Running

## Requirements
### Accessing services
#### Local
In order to access services on the local network a DNS server is needed that allows to add custom rules to it. Something like https://pi-hole.net or https://adguard.com/en/welcome.html can be used to route custom domains to Traefik. 
With Traefik we can even have valid SSL certs for services running only on the local network using the DNS challange
#### Remote
For hosting services public either a static IP or DynDns is required
Then a domain can be bought allowing the use of subdomains
All (Sub)Domains must point to your public IP
The Router needs to be configured to allow traffic from ports 80 and 443 to the local Traefik container
