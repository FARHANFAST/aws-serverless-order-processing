# Serverless Order Processing System on AWS

##  Project Overview
An event-driven, serverless backend designed to automate e-commerce order workflows. This system handles incoming order requests via a REST API, decouples processing through message queues, stores order data in a NoSQL database, and triggers real-time notifications.

##  Architecture
The system utilizes a fully serverless stack to ensure high availability and automatic scaling:

1. **Entry Point:** Amazon API Gateway receives POST requests.
2. **Processing:** AWS Lambda parses the payload and coordinates downstream tasks.
3. **Decoupling:** Amazon SQS (FIFO) ensures orders are queued reliably and processed in the exact order received.
4. **Persistence:** Amazon DynamoDB stores order metadata and history.
5. **Notification:** Amazon SNS triggers automated email confirmations to customers.

##  Tech Stack
* **Languages:** Python (Boto3 SDK)
* **Compute:** AWS Lambda
* **API:** Amazon API Gateway
* **Messaging:** Amazon SQS, Amazon SNS
* **Database:** Amazon DynamoDB (NoSQL)
* **Security:** AWS IAM (Custom Least-Privilege Policies)

##  Repository Structure
* `src/`: Contains the core Lambda logic.
* `iam-policies/`: Contains the JSON security policies required for service-to-service communication.
* `tests/`: Contains a sample JSON event used to trigger and test the Lambda function in the AWS console.

##  Key Features & Skills Demonstrated
* **Event-Driven Design:** Built a system that reacts to real-time triggers rather than running 24/7, optimizing costs.
* **Infrastructure Security:** Implemented custom IAM roles to follow the Principle of Least Privilege (PoLP).
* **Scalability:** Leveraged AWS managed services that scale automatically based on incoming traffic.
