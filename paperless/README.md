
docker exec --user 1000 gitea gitea admin user generate-access-token --scopes all --username USER

curl -X POST "https://git.let-net.cc/api/v1/user/applications/oauth2"   -H "Authorization: token <TOKEN>"   -H "Content-Type: application/json"   -d '{
        "name": "Paperless",
        "confidential_client": true,
        "redirect_uris": ["https://docs.let-net.cc/accounts/oidc/gitea/login/callback/"]
      }'

# OIDC SSO
To enable SSO follow the commands in the Gitea Readme to create a new OAuth Application and retrieve the CLIENT_ID and CLIENT_SECRET and set them in the .env file

Then disable:
```yaml
PAPERLESS_DISABLE_REGULAR_LOGIN: true
PAPERLESS_REDIRECT_LOGIN_TO_SSO: true
```
by commenting them out, create a new superuser account and in the profile setting connect it with Gitea SSO.
Then re-enable the option to only allow login via SSO.