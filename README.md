


# Stack Configuration Values for DMSeer

```shell
pulumi config set aws_region                     'ca-central-1'
pulumi config set aws_user_files_bucket          'unknown'
pulumi config set dmseer_admin_username          'Storyteller'
pulumi config set dmseer_discord_redirect_uri    'https://api.quillndice.com/login/discord/callback'
pulumi config set dmseer_uploaded_files          'aws'
pulumi config set postgres_dmseer_user_username  'postgres'
pulumi config set postgres_host                  'localhost'
pulumi config set postgres_username              'postgres'

pulumi config set dmseer_admin_password          '[secret]' --secret
pulumi config set dmseer_discord_bot_token       '[secret]' --secret
pulumi config set dmseer_jwt_secret              'dd6b6dd097cbb664b5362bc44e9df885' --secret
pulumi config set dmseer_postman_apikey          '[secret]' --secret
pulumi config set postgres_dmseer_user_password  'trustlocal' --secret
pulumi config set postgres_password              'trustlocal' --secret
```

Switch to the appropriate stack

```shell
export AWS_PROFILE=local
pulumi stack select local
```

Then create the parameters in SSM

```shell
pulumi up
```


Display the value of a parameter

```shell
aws ssm get-parameter --name /shared-config/local/dmseer/admin_username
```

## Examples

```shell
pulumi config set motd 'Hello from Pulumi!'
pulumi config set motd_secret 'Ssh! This is a secret.' --secret
```

