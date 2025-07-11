# Automate-Daily-Data-Analysis
Automate Daily Data Analysis with Amazon Athena, AWS Lambda &amp; S3
## Tools
### Lambda
### S3
### Athena

## Creating the Lambda code

## S3
Create a bucket
```sh
aws s3 mb s3://my-analysis-buckooo
```
Create folders inside the bucket
raw, athena, processed

## Athena
Configer Athena with a database that will be used to host the table that will have the data querried
