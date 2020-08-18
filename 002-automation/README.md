# Serverless APIs are way better with automation

Building and managing 100s of serverless APIs can be a daunting task. Lucky for us, AWS provided a nice and smooth way of automating
work related to Lambda functions which can include:

- Installing of dependencies on each endpoint
- Releasing to multiple environments (dev, uat and prod)
- Decommissioning of APIs
- Seeding of Dynamo DBs
- Testing behavior

This sections showcases different samples of automation related to Serverless API development.

### Pre-requisites

You will need to run the following in your machine:

- AWS CLI
- AWS SAM CLI
- AWS Account
- Named profile for your AWS CLI
- S3 Bucket for SAM artifact storage
- NodeJS

### Project Tree

```txt
├─red-ninja-get-list            ---> API code for retrieving red ninjas
├─white-ninja-get-list          ---> API code for retrieving white ninjas
│ 001_install_dependencies.sh   ---> Script used for installing node modules
│ 002_release_tables.sh         ---> Script used for provisioning DynamoDBs
│ 003_release_apis.sh           ---> Script used for provisioning APIs
│ 004_decommission_apis.sh      ---> Script used for decommissioning APIs
│ 005_decommission_tables.sh    ---> Script used for decommissioning of DynamoDBs
│ apis.sam.yaml                 ---> SAM Template used for defining API resources
│ README.md                     ---> Section documentation
│ tables.cfn.yaml               ---> Cloud Formation template used for defining DynamoDBs
```