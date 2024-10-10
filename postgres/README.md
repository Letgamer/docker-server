# PGADMIN Postgres Database Manager

pgAdmin is the most popular and feature rich Open Source administration and development platform for PostgreSQL, the most advanced Open Source database in the world.

```
.
└── postgres/
    ├── data/
    ├── pgadmin/
    ├── docker-compose.yaml
    └── docker-compose.config.yaml
```

The docker-compose.yaml contains the default configuration to start the Application.

It gets extended by a docker-compose.config.yaml which sets config options, mostly oauth2.

A .env File is needed with the following contents:

```
DB_PASSWORD=

MAIL=test@test.de

ADMINPASS=

DOMAIN=example.com

OAUTH_ID=

OAUTH_SECRET=
```

OAUTH ID and Secret can be generated in Gitea under User -> Settings -> Applications

Start the containers with the following command:
```
docker compose -f docker-compose.yaml -f docker-compose.config.yaml up -d
```
