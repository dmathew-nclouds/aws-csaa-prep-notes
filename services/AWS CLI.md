# Examples

* `aws configure`: Give the keys from CSV which is downloaded when user is created, default region name: e.g. for london => `eu-west-2`
* `aws s3 ls`: List all the buckets
* `aws s3 help`
* Configs are credentials are in => `~/.aws`
* `aws ec2 describe-instances`
* `aws ec2 terminate-instances --instance-ids INSTANCE_ID`
* `aws s3 cp --recursive s3://... /home/localuser` => Copy s3 bucket to `/home/localuser` path. You need to give `--region` option if bucket is located in different region.