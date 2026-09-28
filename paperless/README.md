# Outline - Notes Manager

The fastest knowledge base for growing teams. Beautiful, realtime collaborative, feature packed, and markdown compatible.

```
.
└── outline/
    ├── paperless/
    ├── redis/
    ├── docker-compose.yaml
    ├── .env
    └── README.md
```

A .env File is needed with the following contents:
```
PAPERLESS_SECRET_KEY=

DOMAIN=example.com

CLIENT_ID=

CLIENT_SECRET=
```

# OIDC SSO
For `CLIENT_ID` and `CLIENT_SECRET` generate new Gitea OAuth2 Application with the following `redirect_url`:
```
https://docs.DOMAIN/accounts/oidc/gitea/login/callback/
```
Refer to the Gitea Readme.md on how to do it.

Then disable:
```yaml
PAPERLESS_DISABLE_REGULAR_LOGIN: true
PAPERLESS_REDIRECT_LOGIN_TO_SSO: true
```
by commenting them out, create a new superuser account and in the profile setting connect it with Gitea SSO.
Then re-enable the option to only allow login via SSO.