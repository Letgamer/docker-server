# Outline - Notes Manager

The fastest knowledge base for growing teams. Beautiful, realtime collaborative, feature packed, and markdown compatible.

```
.
└── outline/
    ├── data/
    ├── pgdata/
    ├── docker-compose.yaml
    ├── .env
    └── README.md
```

A .env File is needed with the following contents:
```
SECRET_KEY=

UTILS_SECRET=

DB_PASS=

DOMAIN=example.com

CLIENT_ID=

CLIENT_SECRET=
```
Generate `SECRET_KEY`,`UTILS_SECRET` and `DB_PASS` with:
```
openssl rand -hex 32
```

For `CLIENT_ID` and `CLIENT_SECRET` generate new Gitea OAuth2 Application.
Refere to the Gitea Readme.md on how to do it.

