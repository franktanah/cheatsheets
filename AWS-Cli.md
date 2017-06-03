# AWS Commandline

## E2

list instances

`aws ec2 describe-instances --region=ap-southeast-1`
## S3

create bucket

`aws s3 mb s3://mybucket`

copy file

`aws s3 cp image.jpg s3://mycontainer/image.jpg --acl public-read`