# Serverless

### Installation
```
npm install -g serverless
```

### AWS Credentials Setup
[Serverless Framework - AWS Lambda Guide - Credentials](https://www.serverless.com/framework/docs/providers/aws/guide/credentials/)
```
serverless config credentials --provider aws --key [[key]] --secret [[secret]]
```

Note: Profiles may already be setup on this computer.
Check: `~/.aws/credentials`
If there is a default profile setup a new one for Serverless

```
[default]
aws_access_key_id = AKIAJ...
aws_secret_access_key = O8YS11Z3se...

[serverless]
aws_access_key_id = AKIA...
aws_secret_access_key = 4w2WKiSV/...
```


### Deploying A Function

Deploying All The Function Code (slower, deploys all the code)
```
sls deploy -v
```

Deploy the function update only (faster, just updates the function)
```
sls deploy function -f hello
```


### Invoking a function
```
sls invoke -f [[function name]]
```


### Logging
Fetch the logs and "tail" them
```
sls logs -f hello -t
```

### Deleting / Cleanup
```
sls remove
```


### Creating AWS Lambda Funcs w/ specific runtimes
```
sls create --template aws-nodejs --path nodejs-example
```

### IAM Policy for Lambda Functions

**Call Any Lambda Function**
```
iamRoleStatements:
  - Effect: "Allow"
    Action:
      - "lambda:*"
    Resource:
      - "*"
```


### Environment Variables
```
environment:
    variable1: value1
```

### VPC Parameters
```
vpc:
  securityGroupIds:
    - securityGroupId1
    - securityGroupID2
  subnetIds:
    - subnetId1
    - subnetId2
```
