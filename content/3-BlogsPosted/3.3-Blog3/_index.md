---
title: "Blog 3"
date: 2026-07-05
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---

# TURNING AMAZON CLOUDWATCH INTO A PROACTIVE MONITORING LAYER FOR THE SYSTEM

While learning about operating systems on AWS, I realized that Amazon CloudWatch is not only a tool for checking CPU usage or receiving emails when a server is overloaded. If **Metrics, Logs, Dashboards, and Alarms** are combined properly, CloudWatch can become a central monitoring system that helps detect issues early and supports automated responses.

A good monitoring system does not only tell us that the system has failed. It also helps detect abnormal signs before users are affected.

## 1. What Does Amazon CloudWatch Actually Do?

Amazon CloudWatch is a **Monitoring & Observability** service from AWS. CloudWatch collects data from resources such as EC2, RDS, Lambda, ECS, API Gateway, and many other AWS services.

CloudWatch helps answer three important questions:

- How is the system currently operating?
- Are there any errors or abnormal signs?
- If an issue occurs, how should the system notify or respond automatically?

Therefore, CloudWatch is not just a place to view charts. It is an important component in cloud system operations.

<img src="/workshop-/images/3-BlogsPosted/blog3-cloudwatch-monitoring.png" alt="Amazon CloudWatch Monitoring Architecture" style="max-width: 100%; height: auto;">

## 2. Do Not Only Look at CPU

A common mistake when configuring monitoring is creating alarms only for CPU usage, for example when CPU exceeds 80%.

However, CPU only reflects one part of the system condition. An effective dashboard should monitor multiple metrics at the same time, such as:

- CPU Utilization.
- Memory Usage.
- Disk Space.
- Network In/Out.
- Request Count.
- Error Rate.
- Response Time or Latency.

When these metrics are placed together, operators can analyze the root cause more easily instead of only knowing that the system is slow.

For example, if latency increases but CPU is not high, the root cause may not be compute. It could come from the database, network, or an external API.

## 3. Logs Explain the Root Cause

Metrics show what is happening, while Logs help explain why it is happening.

For example:

- API Error Rate increases.
- The dashboard shows a sudden increase in latency.
- CloudWatch Logs show that the root cause is a database query timeout.

Collecting logs from Lambda, API Gateway, EC2, or applications into CloudWatch makes debugging much faster than checking each server or service separately.

In a serverless architecture, CloudWatch Logs are especially important because Lambda does not have a fixed server that we can SSH into. Most debugging information must be reviewed through logs.

## 4. Alarms Are Not Only for Sending Emails

CloudWatch Alarms are not only used to send email notifications. A good alarm can trigger multiple automated actions, such as:

- Sending emails through Amazon SNS.
- Triggering Auto Scaling.
- Invoking AWS Lambda to handle an issue.
- Triggering Systems Manager Automation.
- Notifying the operations or DevOps team.

This allows the system to respond within seconds instead of waiting for an administrator to investigate manually.

## 5. Practical Example

Assume that an e-commerce website is preparing for a Flash Sale. Traffic increases many times compared to normal days.

CloudWatch can detect:

- CPU exceeds the threshold.
- Request latency increases.
- Error rate starts to appear.
- API Gateway returns many 5xx errors.
- Lambda duration increases abnormally.

At that point, a CloudWatch Alarm can be triggered. The alarm sends a notification to Amazon SNS, and SNS sends an alert email to the operations team.

If automated response is configured, the alarm can also trigger Lambda or Systems Manager to perform remediation actions.

Without good monitoring, users may be the first ones to notice that the website has a problem.

## 6. Applying CloudWatch to My E-commerce Project

In my AWS Serverless E-commerce Platform project, CloudWatch can be used to monitor key components such as:

- API Gateway request count.
- API Gateway 4xx and 5xx errors.
- Lambda errors.
- Lambda duration.
- Lambda throttles.
- EventBridge scheduled job execution.
- Logs from EcommerceBackendFunction.
- Logs from PaymentExpirySchedulerFunction.
- Logs from RefundReconciliationFunction.

When an error occurs, CloudWatch Alarm can send an alert to Amazon SNS. SNS then sends an email to the admin or system operator.

The monitoring flow in the project:

```text
API Gateway / Lambda / EventBridge
   ↓
Amazon CloudWatch Logs & Metrics
   ↓
CloudWatch Alarm
   ↓
Amazon SNS
   ↓
Alert Email
```

## 7. What I Learned

After learning about CloudWatch, I learned several important points.

First, monitoring is not only about checking CPU charts. A system needs to monitor multiple metrics to correctly evaluate its operating condition.

Second, logs play a very important role in finding the root cause of errors, especially in serverless systems such as Lambda.

Third, alarms should be designed to support fast response. They should not only send notifications but can also trigger automated actions.

Fourth, CloudWatch is an important part of production system operations because it helps detect issues early and reduce troubleshooting time.

## 8. Conclusion

Amazon CloudWatch is not only a tool for viewing CPU charts or sending basic alert emails. When Metrics, Logs, Dashboards, and Alarms are combined, CloudWatch can become a proactive monitoring layer for the system.

Effective monitoring is not about knowing that the system has already failed. It is about detecting and handling issues before users are affected.

Through this blog, I gained a better understanding of the role of CloudWatch in AWS operations and how to apply CloudWatch to my serverless e-commerce project.

## 9. References

- Amazon CloudWatch Documentation
- Amazon CloudWatch Logs Documentation
- Amazon CloudWatch Alarms Documentation
- Amazon SNS Documentation
- AWS Lambda Monitoring Documentation
- Amazon API Gateway Monitoring Documentation
