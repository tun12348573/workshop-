---
title: "Blog 1"
date: 2026-07-08
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

# SECURITY RESPONSE AUTOMATION ON AWS

While learning about security services on AWS, I read the article **"How to get started with security response automation on AWS"** on the AWS Security Blog.

What impressed me the most was how AWS builds an automated process to detect and respond to security incidents using an **event-driven architecture**. Instead of requiring the operations team to manually monitor alerts and handle incidents, AWS can combine services such as **AWS CloudTrail, Amazon EventBridge, AWS Lambda, AWS Systems Manager, and Amazon SNS** to create an automated security response pipeline.

This architecture helps the system quickly detect abnormal events, automatically perform remediation actions, and send notifications to the operations team.

## 1. Problem Statement

In an AWS environment, many events can create security risks if they are not handled in time, for example:

- AWS CloudTrail is disabled.
- A Security Group is opened to the entire Internet.
- An Amazon S3 bucket becomes public.
- An IAM Access Key is created or used abnormally.
- An EC2 instance shows signs of being compromised.
- Security Hub or GuardDuty detects a critical finding.

In a traditional approach, the Security or DevOps team has to receive an alert, investigate the root cause, evaluate the impact, and then perform remediation steps manually. This process takes time and depends heavily on human operation.

AWS recommends automating the response process so that the system can react immediately when a security event occurs.

## 2. Overall Architecture

Based on my understanding, the security response automation process works as follows:

```text
Security Event
   ↓
CloudTrail / GuardDuty / AWS Config
   ↓
Amazon EventBridge
   ↓
AWS Lambda
   ↓
AWS Systems Manager Automation
   ↓
Remediation + SNS Notification
```

The key point of this architecture is that the workflow is only triggered when a security event occurs. As a result, resources are used efficiently and the response time is much faster than manual handling.

<img src="/workshop-/images/3-BlogsPosted/blog1-security-response.png" alt="Security Response Automation Architecture" style="max-width: 100%; height: auto;">

## 3. Role of Each Service

### AWS CloudTrail

AWS CloudTrail records API activities in an AWS account. It is an important data source for detecting abnormal actions such as disabling logging, creating new access keys, changing security groups, or making an S3 bucket public.

### Amazon EventBridge

Amazon EventBridge listens for events. When CloudTrail, AWS Config, GuardDuty, or Security Hub generates an event that matches a configured rule, EventBridge automatically triggers the next processing step.

### AWS Lambda

AWS Lambda is used to perform automated remediation actions. For example:

- Re-enable CloudTrail if it is disabled.
- Update a Security Group to close public ports.
- Revoke or disable suspicious IAM Access Keys.
- Call Systems Manager Automation for more complex workflows.

### AWS Systems Manager

AWS Systems Manager is used when the remediation workflow requires multiple steps, such as isolating an EC2 instance, running an automation document, or performing remediation based on a predefined scenario.

### Amazon SNS

After the remediation process is completed, Amazon SNS sends notifications to the operations or security team so they can review and monitor the result.

## 4. Workflow

The workflow can be described as follows:

1. A security event occurs in the AWS account.
2. CloudTrail or another security service records the event.
3. EventBridge detects an event that matches a configured rule.
4. EventBridge triggers Lambda.
5. Lambda performs remediation or calls Systems Manager Automation.
6. SNS sends a notification to the operations team.
7. CloudWatch Logs records the remediation process for later review.

The entire process can be completed in a short time without manual operation.

## 5. What I Learned

After studying the article, I learned several important points.

First, detecting a security incident is not enough. A good security system also manual operation.

## 5. What I Learned

After studying needs the ability to respond quickly and automate repetitive remediation steps.

Second, an event-driven architecture is very suitable for security use cases because the system only runs when an event occurs. This helps optimize cost and makes the system easier to scale.

Third, combining CloudTrail, EventBridge, Lambda, Systems Manager, and SNS can create a flexible security pipeline that can be applied to many scenarios, such as:

- Remediating public S3 buckets.
- Closing Security Groups that are open to the Internet.
- Revoking suspicious IAM Access Keys.
- Isolating suspected compromised EC2 instances.
- Handling Security Hub Findings.

## 6. Conclusion

Through this blog, I gained a better understanding of how AWS builds a **Security Response Automation** system by combining serverless and managed services.

The most valuable point is the ability to automatically detect and respond almost in real time. This reduces dependency on manual operations, shortens incident response time, and improves security operations.

In the future, I would like to try implementing this architecture to better understand how AWS services work together in a real-world security system.

## 7. References

- AWS Security Blog: How to get started with security response automation on AWS
- AWS CloudTrail Documentation
- Amazon EventBridge Documentation
- AWS Lambda Documentation
- AWS Systems Manager Documentation
- Amazon SNS Documentation
