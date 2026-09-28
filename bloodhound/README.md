# Bloodhound CE

BloodHound is a cybersecurity tool that visualizes relationships and attack paths in an active directory environment, helping in identifying privilege-escalation and access-control weaknesses.

```
.
└── bloodhound/
    ├── neo4j-data/
    ├── neo4j-logs/
    ├── postgres-data/
    ├── .env
    └── docker-compose.yaml
```

A .env File is needed with the following contents:

```
# Postgres auth configuration
POSTGRES_PASSWORD=

# Auth string for NEO4J credentials
NEO4J_SECRET=

JWT=

DOMAIN=example.com

PASSWORD=
```

The password is used for the admin account that allows logging in via `admin@admin`.
