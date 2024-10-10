# Gitea - Alternative to Github

Git with a cup of tea! Painless self-hosted all-in-one software development service, including Git hosting, code review, team collaboration, package registry and CI/CD

```
.
└── gitea/
    ├── gitea
    ├── postgres
    ├── public
    ├── docker-compose.yaml
    ├── .env
    └── README.md
```
The public folder contains a custom [github-like](https://github.com/Rainnny7/gitea-github-theme) theme and custom logos

A .env file is needed with the following contents:

```
DOMAIN=example.com

POSTGRES=gitea

POSTGRES_PWD=

TITLE=
```

Gitea is also used as an OAuth2 Provider!

Admin Account Creation has to happen via cli with the following command:
```
docker exec --user 1000 gitea gitea admin user create --admin --username USER --password PASS --email test@test.de --access-token --must-change-password=false
```
Generate an Access Token to use the API:
```
docker exec --user 1000 gitea gitea admin user generate-access-token --scopes all --username USER
```

Generate a new OAuth2 application:
```
curl -X POST "http://your-gitea-instance/api/v1/user/applications/oauth2" \
  -H "Authorization: token YOUR_ACCESS_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
        "name": "Your App Name",
        "redirect_uris": ["http://yourapp.com/callback"]
      }'

```


TODO:
- Database needs to be migrated from postgres 16 -> 17
