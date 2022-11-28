**Access Policy for S3 Bucket to SQS**

```
{
  "Version": "2012-10-17",
  "Id": "example-ID",
  "Statement": [
    {
      "Sid": "example-statement-ID",
      "Effect": "Allow",
      "Principal": {
        "Service": "s3.amazonaws.com"
      },
      "Action": "SQS:SendMessage",
      "Resource": "sqs-arn-id",
      "Condition": {
        "StringEquals": {
          "aws:SourceAccount": "aws-account-id"
        },
        "ArnLike": {
          "aws:SourceArn": "s3-bucket-arn-id"
        }
      }
    }
  ]
}

```
