# Serverless Event-Driven Image Resizer

An automated cloud pipeline built with **Terraform** and **AWS Lambda** that generates image thumbnails in real-time. This project demonstrates Infrastructure as Code (IaC), event-driven architecture, and proactive cloud monitoring.

## 🚀 Features
* **Infrastructure as Code:** Entire AWS stack (S3, Lambda, IAM, CloudWatch) managed via Terraform.
* **Event-Driven Processing:** S3 'ObjectCreated' events trigger Lambda functions instantly.
* **Cross-Platform Compatibility:** Packaged with `manylinux` Pillow binaries to ensure seamless execution in AWS Linux environments.
* **Observability:** Custom CloudWatch Dashboard for tracking throughput and performance.
* **Proactive Alerting:** Integrated SNS (Simple Notification Service) email alerts for system failures.

## 🛠️ Architecture
1.  **User** uploads a high-res image to the `raw-images` S3 bucket.
2.  **S3** triggers a Lambda function via an asynchronous event.
3.  **AWS Lambda** (Python 3.11) resizes the image using the Pillow library.
4.  **S3** stores the optimized thumbnail in the `thumbnails` bucket.
5.  **CloudWatch** monitors the process, updating a dashboard and triggering an **SNS email alarm** if an error occurs.

## 🔧 Technical Stack
* **Provider:** AWS
* **IaC:** Terraform
* **Language:** Python (Pillow library)
* **Monitoring:** CloudWatch Metrics, Alarms, & Dashboards
* **Messaging:** SNS

## 📈 Monitoring & Reliability
The system includes a production-grade monitoring suite:
* **Dashboards:** Visualizing successful vs. failed executions.
* **Alarms:** Automatic email notifications via SNS if the failure threshold is exceeded.