# Vaultwarden Password Manager

Vaultwarden is a alternative implementation of the Bitwarden server API written in Rust and compatible with upstream Bitwarden clients.

```
.
└── vaultwarden/
    ├── data/
    ├── .env
    └── docker-compose.yaml
```

The docker-compose.yaml contains the default configuration to start the Vaultwarden Server.

A full documentation of the available environment variables can be found here:
https://github.com/dani-garcia/vaultwarden/blob/main/.env.template

A .env File is needed with the following contents:

```
VAULTWARDEN_DOMAIN=vaultwarden.example.com

PUSH_INSTALLATION_ID=

PUSH_INSTALLATION_KEY=
```

Push ID and Key is needed to enable push notifications on mobile clients and can be recieved from here: https://bitwarden.com/host/

At first install set an `ADMIN_TOKEN` and goto `/admin` and setup an Account, then remove the `ADMIN_TOKEN`
