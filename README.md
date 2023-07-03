EasyDNS module for Caddy
===========================

This package contains a DNS provider module for [Caddy](https://github.com/caddyserver/caddy). It can be used to manage DNS records with [EasyDNS](https://easydns.com/).

## Caddy module name

```
dns.providers.easydns
```

## Config examples

To use this module for the ACME DNS challenge, [configure the ACME issuer in your Caddy JSON](https://caddyserver.com/docs/json/apps/tls/automation/policies/issuer/acme/) like so:

```json
{
	"module": "acme",
	"challenges": {
		"dns": {
			"provider": {
				"name": "easydns",
				"api_token": "YOUR_PROVIDER_API_TOKEN",
				"api_key": "YOUR_PROVIDER_API_KEY",
				"api_url": "https://rest.easydns.net"
			}
		}
	}
}
```

or with the Caddyfile:

```
# globally
{
	acme_dns easydns {
		api_token <your_api_token>
		api_key <your_api_key>
		api_url "https://rest.easydns.net"
	}
}
```

```
# one site
tls {
	dns easydns {
		api_token <your_api_token>
		api_key <your_api_key>
		api_url "https://rest.easydns.net"
	}
}
```
