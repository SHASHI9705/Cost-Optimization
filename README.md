Project Title: Automated Cost Optimization using AWS Lambda

Description:
This project demonstrates how to reduce AWS costs by automatically identifying and stopping underutilized EC2 instances using AWS Lambda. By monitoring CPU utilization via CloudWatch and automating the stop action through Lambda, unnecessary compute charges are minimized.

Key Features:
- Detects EC2 instances with consistently low CPU usage
- Uses CloudWatch alarms to monitor performance
- Sends alerts via SNS
- Triggers a Lambda function to stop unused instances
- Uses IAM roles to grant necessary permissions securely

Technologies Used:
- AWS Lambda (Python)
- Amazon EC2
- Amazon CloudWatch
- Amazon SNS
- AWS Identity and Access Management (IAM)
- AWS SDK for Python (Boto3)

Implementation Steps:
1. Prerequisites
   - AWS account
   - Running EC2 instances
   - IAM permissions to access EC2, CloudWatch, Lambda, and SNS

2. Create IAM Role
   - Attach the following policies:
     - AmazonEC2ReadOnlyAccess
     - AmazonEC2FullAccess
     - AWSLambdaBasicExecutionRole

3. Set Up CloudWatch Alarm
   - Monitor EC2's CPUUtilization metric
   - Set a threshold (e.g., less than 5% for 1 hour)
   - Link alarm to SNS topic

4. Configure SNS Topic
   - Create a topic that receives CloudWatch alarm notifications
   - Set up subscription for Lambda function trigger

5. Create Lambda Function
   - Language: Python 3.x
   - Use Boto3 to interact with EC2 and CloudWatch
   - Fetch CPU metrics and stop instances if threshold is met

6. Assign IAM Role to Lambda
   - Grant necessary permissions using the role created in Step 2

7. Test Setup
   - Lower EC2 workload manually
   - Confirm that CloudWatch alarm triggers
   - Validate that Lambda stops the idle instance

8. Monitor and Improve
   - Use CloudWatch Logs to debug and review Lambda performance
   - Tune CPU thresholds as needed
   - Extend functionality to notify users or tag instances



Author: Shashiranjan singh
