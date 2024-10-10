# Tailscale VPN

The easiest, most secure way to use WireGuard and 2FA.

```
.
└── tailscale/
    ├── data/
    ├── docker-compose.yaml
    ├── .env
    └── README.md
```

Create an Account at https://login.tailscale.com/

A .env File is needed with the following contents:

```
TS_AUTHKEY=

TS_HOSTNAME=

ROUTES=
```
Generate the auth key under https://login.tailscale.com/admin/settings/keys

Set Routes to the subnet of the server to make it accessible to VPN Users
e.g. 192.168.178.0/24

After starting up the container disable key expiry for the server on the Dashboard and allow the Use as an Exit Node!

Now connecting to the server is possible by downloading tailscale client apps. The Server is available under the set Hostname
