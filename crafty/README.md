# Crafty Controller

Crafty 4 is a modern and fast Minecraft Server Web Management Frontend

```
.
└── crafty/
    ├── crafty
    ├── docker-compose.yaml
    ├── .env
    └── README.md
```

Crafty itself automatically generates admin credentials under `crafty/app/config/default-creds.txt`

To make the Minecraft Server reachable under minecraft.example.com without Port Forwarding a Tunnel is needed

# PlayIt

playit.gg is a global proxy that allows anyone to host a server without port forwarding

1. Create an Account on playit.gg
2. Go to Agents and create a docker based Agent to get the `SECRET_KEY` and save it in the `.env` file
3. After connecting select the created Agent on the Dashboard and Add a Minecraft Java Tunnel
4. Set the local Address to `10.1.0.100:25565`
5. Copy the provided IP and Port

A .env File is needed with the following contents:
```
DOMAIN=example.com

SECRET_KEY=
```

## Domain Setup

1. Create an SRV Record:
- Name: _minecraft._tcp.mc
- Priority: 0
- Weight: 0
- TTL: Auto
- PORT: INSERT THE PROVIDED PORT HERE!
- Target: mc.my-domain.com

2. Create an A Record:
- Name: mc
- IPv4 address: INSERT THE PROVIDED IP HERE!

After that the Minecraft Server is reachable on your subdomain, in this case: `mc.`
