# Traefik + cloudflare tunnel

Traefik is used as a internal reverseproxy and tunneled into the world wide web through a cloudflare tunnel.

```
.
└── proxy-tunnel/
    ├── cloudflared/
    ├── docker-compose.conf.yaml
    ├── docker-compose.yaml
    ├── .env
    └── README.md
```

The docker-compose contains two different services. The cloudflared service and the traefik service both connected by a network.

## Cloudflared:

All settings for cloudflared are stored in the cloudflared folder.

It creates the tunnel-uuid.json and cert.pem automatically when logging in:

`docker run -v $PWD/cloudflared:/etc/cloudflared cloudflare/cloudflared login`

and setting up a tunnel:

`docker run -v $PWD/cloudflared:/etc/cloudflared cloudflare/cloudflared tunnel create mytunnel`

'$PWD' has to be replaced with the absolute path!

The config.yml ist the most important file for cloudflared. The main configuration is handeled there

Two rules are important to create in there:

1. The Wildcard Rule which passes every possible subdomain to traefik
2. The service which is required to start the container and functions as a catch for all invalid requests

A .env File is needed with the following contents:
```
DOMAIN=example.com
UUID=
```
You can get the UUID from the cloudflared folder after setting up the tunnel!

## Traefik:

Traefik is configured through environment variables located in the docker-compose.yaml file.


## Startup

Start the Containers with the following command:

`docker compose -f docker-compose.yaml -f docker-compose.conf.yaml up -d`
