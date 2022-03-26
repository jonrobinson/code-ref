# Email Import

https://aws.amazon.com/premiumsupport/knowledge-center/ses-receive-inbound-emails/

### Step 1: Verify the Email Domain
Source: https://docs.aws.amazon.com/ses/latest/dg/creating-identities.html#verify-domain-procedure
1. Go to SES (Simple Email Service)
2. Verified Identities
3. Choose "Create Identity"
4. Under Identity details, select Domain as the type of identity you want to create. You must have access to the domain’s DNS settings to complete the domain verification process.
a. INPUT DOMAIN: example.com (do primary domain first then ses.example.com)
b. UNCHECKED: Assign a default configuration set && Use a custom MAIL FROM domain
c. CHECK: Easy DKIM
d. CHECK RSA_2048_BIT
e. Publish DNS records to Route53 (if on Route53)
f. DKIM signatures (Enabled)
(REPEAT FOR SUBDOMAIN)

### Step 2: Setup Bucket w/ put Permissions from SES
Source: https://aws.amazon.com/premiumsupport/knowledge-center/ses-receive-inbound-emails/
Note:
1. Replace AWSDOC-EXAMPLE-BUCKET with the name of your bucket.
2. Then, replace 111122223333 with your AWS account ID.
```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "AllowSESPuts",
            "Effect": "Allow",
            "Principal": {
                "Service": "ses.amazonaws.com"
            },
            "Action": "s3:PutObject",
            "Resource": "arn:aws:s3:::AWSDOC-EXAMPLE-BUCKET/*",
            "Condition": {
                "StringEquals": {
                    "aws:Referer": "111122223333"
                }
            }
        }
    ]
}
```

### Step 3: Create Lambda Function to notify the backend
See notes using serverless for Notify

### Step 3: Create an Amazon SES receipt rule that sends inbound emails to the S3 bucket
High Level, you create a "Rule Set" we only can use one so we just name it default.
This RuleSet will have a Rule "ImportToS3" which will have two actions:
1. Action 1: Delivery the inbound emails to the S3 bucket
2. Action 2: Invoke a lambda function to notify the backend

Source: https://aws.amazon.com/premiumsupport/knowledge-center/ses-receive-inbound-emails/

1. Goto: SES > Email Receieving > Create Rule Set
2. Name: default-rule-set
3. Click: "Set as Active"
4. Click: "Create Rule"
5. Name: ImportToS3
a. CHECKED: Status && Spam and virus scanning
6. Recipient Conditions: imports@ses.boomboxgifts.com
7. New Action (Action 1)
a. Deliver to S3 Bucket
b. select bucket of choice
c. Specify an appropriate Object Key prefix (e.g: task-emails, customer-service-emails)
