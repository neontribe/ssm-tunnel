# ssm-tunnel
Uses a pip file set up the SSM tunnel

~/.aws/config
```
[default]
region = eu-west-2
output = json
aws_default_endpoint = http://localhost:4566

[profile ncvo-dev]
role_arn=arn:aws:iam::XXXXXXXXXXXXXXXX:role/NeonTribe
source_profile=ncvo
region = eu-west-2
output = json

[profile ncvo-int]
role_arn=arn:aws:iam::XXXXXXXXXXXXXXXX:role/NeonTribe
source_profile=ncvo
region = eu-west-2
output = json

[profile ncvo-staging]
role_arn=arn:aws:iam::XXXXXXXXXXXXXXXX:role/NeonTribe
source_profile=ncvo
region = eu-west-2
output = json

[profile ncvo-prod]
role_arn=arn:aws:iam::XXXXXXXXXXXXXXXX:role/NeonTribe
source_profile=ncvo
region = eu-west-2
output = json
```

~/.aws/credentials 
```
[default]
aws_access_key_id = XXXXXXXXXXX
aws_secret_access_key = XXXXXXXXXXXXXXXXX
region=eu-west-1

[ncvo]
aws_access_key_id = XXXXXXXXXXX
aws_secret_access_key = XXXXXXXXXXXxp
region = eu-west-2
```

```
DEV      AWS_PROFILE=ncvo-dev ssm-tunnel --region eu-west-2 BastionHost --route 10.50.218.179/32
INT      AWS_PROFILE=ncvo-int ssm-tunnel --region eu-west-2 BastionHost --route 10.51.160.157/32
STAGING  AWS_PROFILE=ncvo-staging ssm-tunnel --region eu-west-2 BastionHost --route 10.52.239.36/32          
PROD     AWS_PROFILE=ncvo-prod ssm-tunnel --region eu-west-2 BastionHost --route 10.53.250.122/32
```
