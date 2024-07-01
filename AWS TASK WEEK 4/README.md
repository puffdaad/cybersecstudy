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
![image showing the final step](<AWS TASK WEEK 4/img5CT.png>)

#### Why do we need cloudtrail logging in the cloud enviroment
Amazon CloudTrail is a crucial service in AWS for governance, compliance, operational auditing, and risk management. Here are some key reasons why CloudTrail is essential in cloud environments:

## 1. Governance and compliance
- **Audit Trail**: CloudTrail provides a record of actions taken by a user, role, or an AWS service in your AWS account. This audit trail helps demonstrate compliance with regulatory standards and internal policies.
- **Regulatory Compliance**: Many industries require detailed logging of user activities for compliance with regulations such as GDPR, HIPAA, SOC 2, and PCI DSS. CloudTrail helps meet these requirements by logging and storing audit data securely.

## 2. Security and Risk Management
- **Security Analysis**: By capturing detailed information about every API call made in your AWS account, CloudTrail aids in analyzing security incidents and tracing steps leading to a security event.
- **Detecting Anomalies**: Integration with AWS CloudWatch and other monitoring services enables the detection of unusual activity patterns, indicating potential security breaches or malicious activities.

## 3. Operational Auditing
- **Troubleshooting**: CloudTrail logs help troubleshoot operational issues by tracking changes to AWS resources and identifying the root cause of issues.
- **Change Tracking**: Keeping track of changes in your environment helps understand who made specific changes and when, aiding in effective incident response and problem resolution.

## 4. Integration with other services
- **AWS Config**: CloudTrail integrates with AWS Config to provide a detailed history of configuration changes to your AWS resources, aiding in configuration compliance and management.
- **Amazon CloudWatch**: Logs from CloudTrail can be sent to CloudWatch for real-time monitoring and alerting on specific activities, enhancing overall monitoring capabilities.

##### What is cloudwatch and how to setup cloudwatch alarms on AWS
Amazon CloudWatch is a powerful tool for monitoring, managing, and optimizing your AWS environment. By leveraging its extensive features, you can gain deep insights into your infrastructure and applications, enhance operational efficiency, and ensure high availability and performance.

## key features
1. **Metrics Collection and Monitoring**
   - **Collect and Track Metrics**: CloudWatch collects and tracks metrics from AWS resources such as EC2 instances, DynamoDB tables, RDS instances, and many others. You can also publish your own custom metrics.
   - **Pre-built and Custom Dashboards**: Use pre-built dashboards or create custom ones to visualize your metrics.

2. **Log Collection and Analysis**
   - **Centralized Logging**: Aggregate, monitor, and analyze log files from various AWS services like EC2, Lambda, CloudTrail, and VPC Flow Logs.
   - **Log Insights**: Use CloudWatch Logs Insights to query and analyze log data.

3. **Alarms**
   - **Set Alarms**: Define thresholds for your metrics and set alarms to notify you when they are breached. This helps in proactive monitoring and issue resolution.
   - **Actions on Alarms**: Configure alarms to take actions like sending notifications via SNS, executing Lambda functions, or automatically scaling resources.

4. **Events**
   - **Event Detection and Response**: CloudWatch Events enables you to respond to state changes in your AWS resources. You can automate workflows based on events.
   - **Rule-Based Filtering**: Define rules to filter events and route them to target AWS services.

5. **Application Insights**
   - **Observability for Applications**: Gain insights into application performance and health by collecting and analyzing application metrics and logs.
   - **Root Cause Analysis**: Quickly identify and diagnose issues impacting your applications.

## How to setup Cloudwatch with Cloudtrail on AWS

## 1. Enable CloudTrail

Ensure that Amazon CloudTrail is enabled to capture AWS API call logs.

 - **Enable CloudTrail**:
  - Navigate to the [AWS Management Console](https://aws.amazon.com/console/) and go to the CloudTrail service.
  - Click on **Trails** in the left-hand menu.
  - Click **Create trail** and follow the wizard to create a new trail.
  - Configure settings such as trail name, storage location (optional), and whether to log data events.
  - Ensure the trail is configured to log management and data events as needed.


## 2. Create a CloudWatch Log Group

Create a CloudWatch log group to receive CloudTrail logs.

- **Create a CloudWatch Log Group**:
  - Navigate to the [AWS Management Console](https://aws.amazon.com/console/) and go to the CloudWatch service.

  ![Cloudwatch page](<AWS TASK WEEK 4/img1CW.png>)

  - Click on **Logs** in the left-hand menu and then click **Log groups**.
  - Click **Create log group**.
  - Enter a name for your log group, e.g., `CloudTrailLogs`.
  - Click **Create log group** to confirm.

## 3. Set Up Subscription Filters 

Set up subscription filters to route specific CloudTrail events to CloudWatch Logs.

- **Create Subscription Filters**:
  - In the CloudWatch console under **Log groups**, select your CloudTrail log group (`CloudTrailLogs`).
  - Click **Create metric filter** to define a filter pattern for specific events or fields within your CloudTrail logs.
  - Assign a metric name and create a new metric based on the filter pattern.

 ## 3. Set Up Subscription Filters 

Set up subscription filters to route specific CloudTrail events to CloudWatch Logs.

- **Create Subscription Filters**:
  - In the CloudWatch console under **Log groups**, select your CloudTrail log group (`CloudTrailLogs`).
  - Click **Create metric filter** to define a filter pattern for specific events or fields within your CloudTrail logs.
  - Assign a metric name and create a new metric based on the filter pattern.


## 4. Create CloudWatch Alarms 

Set up CloudWatch alarms to be notified when specific events occur.

- **Create CloudWatch Alarms**:
  - In the CloudWatch console, navigate to **Alarms** in the left-hand menu.
  - Click **Create alarm**.
  - Select the metric generated by your subscription filter.
  - Configure the alarm threshold (e.g., threshold value, period, actions).
  - Specify actions such as sending notifications via Amazon SNS or executing AWS Lambda functions.

## 5. Link CloudTrail to CloudWatch Events 

Automate responses to CloudTrail events by configuring CloudWatch Events.

- **Create CloudWatch Events Rules**:
  - In the CloudWatch console, navigate to **Events** in the left-hand menu.
  - Click **Create rule**.
  - Define the rule based on event patterns, such as specific API actions captured by CloudTrail.
  - Configure targets for the rule, such as Lambda functions, EC2 instances, or other AWS services.

