# Automate-Daily-Data-Analysis
Automate Daily Data Analysis with Amazon Athena, AWS Lambda &amp; S3
## Tools
### Lambda
### S3
### Athena
### IAM

## Creating the Lambda code

## S3
Create a bucket
```sh
aws s3 mb s3://my-analysis-buckooo
```
Create folders inside the bucket
raw, athena, processed

## Athena
Configure Athena with a database that will be used to host the table that will have the data querried
- Select the S3 bucket and choose athena folder as the Query result location
- Create a database called `analysis_db`
## IAM
Create an IAM role called `analysis-policy`that is gonna be used by lambda to communinicate with S3 and Athena
- AmazonS3FullAccess
- AmazonAthenaFullAccess
- AmazonAPIGatewayPushToCloudWatchLogs
