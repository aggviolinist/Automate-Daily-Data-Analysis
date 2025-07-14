# Automate-Daily-Data-Analysis
Automated pipeline that analyzes your data files daily without the need for any servers.
## Tools
### Lambda
### S3
### Athena
### IAM
### EventBridge

## Creating the Lambda code
1. Creates an Athena table pointing to CSV data in S3.
2. Runs a query on that table to find kombucha records with abnormal pH levels.
3. Writes query results to a specific folder in an S3 bucket.
4. Returns the location of the results in S3.
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
## Lambda
Upload out lambda code to lambda and deploy it
## EventBridge
Create a rule that runs 9pm daily. It uses the lambda function to clean the data from S3 using Athena.
