# Cloudtrail logging
 Amazon CloudTrail is a service that enables governance, compliance, and operational and risk auditing of your AWS account. It logs, continuously monitors, and retains account activity related to actions across your AWS infrastructure. This includes actions taken through the AWS Management Console, AWS SDKs, command line tools, and other AWS services.
## How to setup cloudtrail on AWS 
### Step 1: Sign in to AWS Management Console
- Go to the [AWS Management Console](https://aws.amazon.com/console/).

- Sign in with your AWS credentials.
### Step 2: Open the CloudTrail Console
- In the AWS Management Console, type "CloudTrail" in the search bar and select **CloudTrail** from the results.

![markdown logo](<AWS TASK WEEK 4/img1CT.png>)

### Step 3: Create a Trail
1. **Create a New Trail**:
   - In the CloudTrail console, click on **Create trail**.
2. **Configure Trail Settings**:
   - **Trail name**: Enter a name for your trail.
   - **Apply trail to all regions**: Select this option if you want the trail to log events from all regions.

   ![markdown logo](<AWS%20TASK%20WEEK%204/img2CT.png>) 
3. **Configure Storage Location**:
   - **Create a new S3 bucket**: If you want CloudTrail to create a new S3 bucket to store log files.
   - **Specify an existing S3 bucket**: If you want to use an existing S3 bucket, provide the bucket name.

   ![markdown logo](<AWS TASK WEEK 4/img2CT.png>)
   - **select Data events and management events, scroll down and click create trail

   ![markdown logo](<AWS TASK WEEK 4/img3CT.png>)
4. **Optional Settings**:
   - **Log file SSE-KMS encryption**: Enable this option if you want to encrypt the log files using an AWS Key Management Service (KMS) key.
   - **CloudWatch Logs**: You can configure CloudTrail to send logs to CloudWatch Logs for real-time monitoring.
   - **SNS notification**: Optionally, configure Simple Notification Service (SNS) to receive notifications about log file delivery.
5. **Create the Trail**:
   - Review the settings and click **Create trail**.


   ![markdown logo](<AWS TASK WEEK 4/img4CT.png>)
   ### Now you have created a cloudtraill logging on AWS
   in the next steps i will explain how to create cloudwatch on AWS


   
   ![markdown logo](https://github.com/puffdaad/cybersecstudy/blob/main/AWS%20TASK%20WEEK%204/img1CT.png)

   ![alt text](https://github.com/puffdaad/cybersecstudy/blob/main/AWS%20TASK%20WEEK%204/img1CT.png)
   
    ![markdown logo](<AWS%20TASK%20WEEK%204/img2CT.png>) 