# Immich Image Management

Immich is a High performance self-hosted photo and video management solution. Allowing to easily back up, organize, and manage your photos on your own server.

```
.
└── immich/
    ├── library/
    ├── model-cache/
    ├── postgres/
    ├── .env
    └── docker-compose.yaml
```

The docker-compose.yaml contains the immich-server, machine learning container and Redis and Postgres.

The latest docker-compose and .env templates can be downloaded from here:  
[docker-compose.yml](https://github.com/immich-app/immich/releases/latest/download/docker-compose.yml) 
[example.env](https://github.com/immich-app/immich/releases/latest/download/example.env)

Just modify the .env file, change the `DB_PASSWORD` and add the `DOMAIN` Variable.

## mTLS

The Immich instance should be configured to use mutual TLS so ensure that the Server is not publicly accessible.  
This can be done by generating a Client Certificate via Cloudflare and direct the Cloudflare WAF to block access to the Host otherwise.

Follow this Tutorial for Setup:

https://kcore.org/2024/06/28/using-cloudflare-zerotrust-and-mtls-with-home-assistant-via-the-internet/


