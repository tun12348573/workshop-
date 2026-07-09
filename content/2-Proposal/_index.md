---
title: "Proposal"
date: 2026-05-11
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# Mimi Jewelry E-commerce Platform

## Serverless E-commerce Solution on AWS

### 1. Executive Summary

The AWS Serverless E-commerce Platform is an e-commerce website system built and deployed on the AWS platform following a serverless model. The project allows users to access the website, browse product lists, view product details, place orders, complete online payments, and track order statuses.

The system features an administration panel for admins to manage products, product images, orders, payment statuses, and refunds. The project utilizes AWS services such as Amazon Route 53, AWS WAF, Amazon CloudFront, Amazon S3, Amazon Cognito, Amazon API Gateway, AWS Lambda, Amazon DynamoDB, Amazon EventBridge, Amazon CloudWatch, Amazon SNS, AWS IAM, and AWS CloudFormation.

Additionally, the system integrates ZaloPay as a third-party payment service and uses GitHub Actions to automate the deployment process. The objective of the project is to build a practical, highly scalable e-commerce system that minimizes manual server management and aligns with modern cloud architectures.

### 2. Problem Statement

*Current Problem* Traditional e-commerce websites usually require backend servers, database servers, image storage systems, user authentication systems, payment processors, monitoring, and CI/CD pipelines. When deployed using a traditional server model, developers must manually manage servers, configure security, handle scaling, perform backups, maintain logging, and resolve operational errors.

This poses significant challenges for personal projects or small teams due to the substantial time required for infrastructure configuration, potential cost increases from continuously running servers, and the added complexity of scaling when traffic surges.

*Solution* This project adopts an AWS Serverless architecture to eliminate server management overhead. Users access the website through a domain managed by Amazon Route 53. Requests are routed through Amazon CloudFront for faster content delivery. AWS WAF is deployed in front of CloudFront to inspect requests and enhance application security against invalid or malicious traffic.

The frontend is stored in an Amazon S3 Frontend Bucket and distributed via CloudFront. Users and admins authenticate through Amazon Cognito. API requests from the frontend pass through Amazon API Gateway and are processed by AWS Lambda. Product and order data are stored in Amazon DynamoDB.

Product images are stored separately in an Amazon S3 Product Image Bucket. When an admin uploads an image, the backend generates an upload URL to store the file into S3, which is then distributed to users via CloudFront.

The system integrates ZaloPay as a third-party payment gateway. When a user completes a checkout, Lambda generates a payment request and sends it to ZaloPay. Upon successful payment, ZaloPay sends a callback to the system to update the order status.

Amazon EventBridge is used to trigger scheduled background tasks, such as checking for overdue pending orders and reconciling refunds. Amazon CloudWatch tracks logs and metrics, while Amazon SNS sends automated alerts to an email address in the event of system errors.

*Benefits and Return on Investment (ROI)* This solution minimizes server operational overhead, scales seamlessly based on request volume, and is ideally suited for small-to-medium-sized e-commerce systems. Utilizing serverless services like S3, CloudFront, API Gateway, Lambda, and DynamoDB optimizes infrastructure costs, as billing is primarily driven by actual consumption.

The project also provides invaluable practical experience in deploying a real-world web application on AWS, covering frontend hosting, serverless backends, NoSQL databases, authentication, file uploads, payment integrations, monitoring, alerting, and CI/CD.

### 3. Solution Architecture

The system is designed around an AWS Serverless architecture. Users access the website via Amazon Route 53, which routes traffic to Amazon CloudFront. Upstream of CloudFront, AWS WAF is configured to inspect requests and protect the application from anomalous traffic.

CloudFront serves the frontend from an Amazon S3 Frontend Bucket. The frontend is a static website built from source code and stored in S3. When users visit the site, CloudFront serves these static assets (HTML, CSS, and JavaScript).

The system utilizes Amazon Cognito for user authentication. Cognito handles logins and issues authentication tokens. These tokens are included by the frontend in headers sent to Amazon API Gateway. API Gateway acts as the API Layer, receiving requests and invoking AWS Lambda functions to handle business logic.

The Compute Layer of the system leverages AWS Lambda. The core Lambda functions include EcommerceBackendFunction, RefundReconciliationFunction, and PaymentExpirySchedulerFunction. EcommerceBackendFunction handles primary business logic such as product management, order processing, checkout, image uploads, payments, and admin operations. RefundReconciliationFunction handles refund status reconciliation. PaymentExpirySchedulerFunction periodically checks for unpaid orders that have exceeded their expiration limit.

The Data Layer utilizes Amazon DynamoDB for persistent storage. The main tables are Products and Orders. Products stores product names, prices, descriptions, image URLs, stock levels, and visibility statuses. Orders tracks order identifiers, customer details, purchased items, total amounts, payment statuses, and fulfillment states.

The S3 Product Image Bucket is dedicated to storing product images. When an admin uploads an image, the backend processes the upload and stores it in this bucket, making it available for display on the website.

The Integration Layer consists of Amazon EventBridge and ZaloPay. EventBridge triggers scheduled background Lambda functions. ZaloPay acts as a Third-Party Service to handle online financial transactions. Lambda transmits payment requests to ZaloPay, which subsequently returns transaction results to the system.

The Monitoring Layer comprises Amazon CloudWatch, Amazon SNS, an Amazon Cognito AdminPool, and an Alert Email. CloudWatch aggregates logs and metrics from API Gateway, Lambda, and other related services. If an error occurs or a performance threshold is breached, CloudWatch sends an alarm to an SNS Topic. SNS then dispatches an email alert to the administrator. The Cognito AdminPool handles administrator authentication within the management portal and controls administrative access rights.

The CI/CD Layer utilizes GitHub, GitHub Actions, an IAM OIDC Role, and CloudFormation. Developers push code to GitHub, where GitHub Actions automatically builds and deploys the system to AWS using an IAM OIDC Role. CloudFormation manages and deploys the entire stack of resources, including Lambda functions, API Gateway, S3 Frontend, CloudFront Invalidation, and associated infrastructure.

<img src="/workshop-/images/2-Proposal/aws-ecommerce-architecture.png" alt="AWS Serverless E-commerce Architecture" style="max-width: 100%; height: auto;">

*AWS Services Utilized*

- *Amazon Route 53*: Manages domain names and DNS routing for the website.
- *AWS WAF*: Inspects requests and hardens application security upstream of CloudFront.
- *Amazon CloudFront*: Distributes the frontend and static assets via a global CDN.
- *Amazon S3 Frontend Bucket*: Stores the static files of the frontend application.
- *Amazon S3 Product Image Bucket*: Stores product catalog images.
- *Amazon Cognito*: Manages user and administrator authentication and sign-ins.
- *Amazon API Gateway*: Receives frontend requests and routes them to Lambda.
- *AWS Lambda*: Executes backend logic, order fulfillment, product catalogs, payments, image uploads, and background tasks.
- *Amazon DynamoDB*: Stores product records and order data.
- *Amazon EventBridge*: Triggers scheduled background Lambda tasks.
- *Amazon CloudWatch*: Records logs, tracks metrics, and manages alerts.
- *Amazon SNS*: Dispatches operational alerts via email.
- *AWS IAM*: Regulates access control and permissions between AWS services.
- *AWS CloudFormation*: Provisions and manages infrastructure using code templates.

*Third-Party Services*

- *ZaloPay*: A third-party payment gateway used to process online transactions.
- *GitHub Actions*: Automates continuous integration and continuous deployment workflows.

*Component Design*

- *User Layer*: Users access the website via the public domain.
- *DNS Layer*: Route 53 routes incoming traffic to CloudFront.
- *Security Layer*: AWS WAF filters requests before they reach CloudFront.
- *Frontend Layer*: CloudFront distributes static assets from the S3 Frontend Bucket.
- *Authentication Layer*: Cognito governs logins and handles validation tokens.
- *API Layer*: API Gateway accepts incoming API calls and forwards them to Lambda.
- *Compute Layer*: AWS Lambda runs all underlying backend business logic.
- *Data Layer*: DynamoDB stores data across the Products and Orders tables.
- *Storage Layer*: S3 Product Image Bucket stores catalog photography.
- *Integration Layer*: EventBridge drives background automations; ZaloPay processes checkouts.
- *Monitoring Layer*: CloudWatch, SNS, and Alert Email capture and report system faults.
- *CI/CD Layer*: GitHub Actions, an IAM OIDC Role, and CloudFormation provision and update the system.

### 4. Technical Implementation

*Implementation Phases*

1. *AWS Services Research*: Learn S3, CloudFront, Route 53, WAF, Cognito, API Gateway, Lambda, DynamoDB, EventBridge, CloudWatch, SNS, IAM, and CloudFormation.
2. *Architecture Design*: Create a comprehensive serverless architectural diagram for the e-commerce system.
3. *Frontend Development*: Build the storefront interface, product detail pages, checkout flow, and administration dashboard.
4. *Backend Development*: Program the backend business logic using Node.js/TypeScript targeted for AWS Lambda execution.
5. *API Layer Configuration*: Set up API Gateway to capture and route incoming client requests.
6. *Database Integration*: Utilize DynamoDB tables to track Products and Orders.
7. *Authentication Integration*: Configure Cognito pools to isolate user and admin logins.
8. *Frontend Deployment*: Upload the built static frontend application to S3 and distribute it via CloudFront.
9. *Security Hardening*: Deploy AWS WAF rules to safeguard the CloudFront distribution.
10. *Image Upload Setup*: Implement an S3 Product Image Bucket to securely store catalog photography.
11. *Payment Integration*: Connect ZaloPay APIs to process payment transactions and receive asynchronous callbacks.
12. *Background Workloads*: Configure EventBridge rules to execute scheduled Lambda routines.
13. *Monitoring and Alerting*: Set up CloudWatch metrics, log groups, alarms, and SNS email streams.
14. *CI/CD Automation*: Wire GitHub Actions with an AWS IAM OIDC Role and CloudFormation for hands-free infrastructure deployment.

*Technical Specifications*

- *Frontend*: Static website architecture hosted on S3 and delivered via CloudFront CDN.
- *Backend*: Node.js/TypeScript runtime environment running on AWS Lambda behind API Gateway.
- *Database*: Schemaless DynamoDB structured into Products and Orders tables.
- *Authentication*: Amazon Cognito user pools segmenting customer and admin identities.
- *Security*: AWS WAF access control lists, IAM policies adhering to least privilege, private S3 buckets, and CloudFront Origin Access Control (OAC).
- *Storage*: Isolated S3 buckets for frontend assets and product images.
- *Payment*: ZaloPay sandbox integration for third-party transaction simulations.
- *Monitoring*: CloudWatch Logs, custom Metrics, Alarms, and SNS notification lists.
- *Deployment*: GitHub Actions CI/CD workflows utilizing IAM OIDC and CloudFormation templates.

### 5. Roadmap & Key Milestones

- *Weeks 1–3*: Core AWS and Serverless Training.
  - Explore the AWS Console, IAM, S3, CloudFront, Route 53, WAF, DynamoDB, Cognito, Lambda, API Gateway, EventBridge, CloudWatch, and SNS.

- *Week 4*: Requirements Analysis & Architectural Design.
  - Define functional specifications.
  - Produce the serverless structural diagram.
  - Finalize the specific selection of target AWS services.

- *Week 5*: Storefront and Admin Frontend Construction.
  - Design home, catalog, and detailed product displays.
  - Build shopping cart flows, checkout interfaces, and administrative tables.

- *Week 6*: Serverless Backend Engineering.
  - Scaffold backend Lambda functions.
  - Model API Gateway resources.
  - Write API endpoints for catalog browse, order submission, and admin actions.

- *Week 7*: DynamoDB Database Integration.
  - Schema design for Products and Orders tables.
  - Establish Lambda data access layers connecting to DynamoDB.

- *Week 8*: Cognito Authentication & Role Authorization.
  - Provision customer and administrative sign-in portals.
  - Enforce JWT token validation and route guards.

- *Week 9*: CloudFront and S3 Frontend Hosting.
  - Compile the web application build.
  - Sync assets to the S3 bucket.
  - Initialize and point the CloudFront distribution.

- *Week 10*: Asset Uploads & Payment Integrations.
  - Configure the S3 Product Image Bucket.
  - Establish presigned URL uploads.
  - Wire ZaloPay transaction endpoints and webhooks.

- *Week 11*: Cron Jobs, Logging & Observability.
  - Set up EventBridge rules.
  - Implement PaymentExpirySchedulerFunction.
  - Implement RefundReconciliationFunction.
  - Deploy CloudWatch alarms paired with SNS alerts.

- *Week 12*: CI/CD Pipelines, Audits & Handover.
  - Code GitHub Actions configuration.
  - Establish IAM OIDC federation.
  - Synthesize CloudFormation templates.
  - Finalize Proposal, Workshop guides, Worklogs, and platform Clean-up.

### 6. Budget Estimation

Operational costs are heavily dependent on request volumes, object storage sizes, data transfer out via CloudFront, CloudWatch log retention policies, and public domain registrations.

*Estimated Infrastructure Costs for Development/Demo Phase*

- Amazon S3: Stores the static frontend and product catalog assets.
- Amazon CloudFront: Distributes assets worldwide via CDN edge servers.
- AWS WAF: Charges apply if Web ACL rules are active.
- AWS Lambda: Billed per function invocation and compute duration.
- Amazon API Gateway: Charged per million requests received.
- Amazon DynamoDB: Charges based on read/write capacity units or storage capacity.
- Amazon CloudWatch: Billed based on log ingestion volumes, custom metrics, and active alarms.
- Amazon SNS: Minimal charges for email distributions.
- Amazon Route 53: Monthly hosted zone fee plus annual registration charges if using a custom domain.
- AWS CloudFormation: Infrastructure management and stack deployment incur no additional fees.

*Expected Total Spend*

- *Development/Demo Phase*: Approximately 0–10 USD / month, assuming traffic is low and unused resources are routinely cleaned up.
- *Custom Domain*: Charged annually if acquired via Route 53.
- *ZaloPay*: Operates completely inside a test/sandbox environment, incurring zero real transaction costs.

### 7. Risk Assessment

*Risk Matrix*

- Flawed IAM configurations or overly permissive policies: High Impact, Medium Probability.
- Misconfigured WAF rules dropping valid requests: Medium Impact, Low Probability.
- Broken S3 bucket policies or CloudFront access issues: Medium Impact, Medium Probability.
- Cognito token synchronization or validation errors during checkout: Medium Impact, Medium Probability.
- Failed payment callbacks or dropped webhooks from ZaloPay: High Impact, Medium Probability.
- Unmonitored CloudWatch Log consumption driving up bills: Medium Impact, Low Probability.
- GitHub Actions deployment failures via OIDC or IAM assumed roles: Medium Impact, Medium Probability.
- Delays in Route 53 domain propagation or HTTPS verification: Low-to-Medium Impact, Medium Probability.

*Mitigation Strategies*

- IAM: Strictly enforce least-privilege access rules across individual roles.
- WAF: Deploy conservative rules first; analyze logs before moving to outright block actions.
- S3/CloudFront: Seal buckets from the public internet using CloudFront Origin Access Control (OAC).
- Authentication: Rigorously parse incoming JWT tokens and cleanly delineate customer vs. admin rights.
- Payments: Verify transaction payload signatures, validate callback URLs, and cross-reference status keys.
- Cost Control: Configure AWS Billing Alerts to detect anomalous cost spikes early and clean up stale infrastructure.
- CI/CD: Scope the IAM OIDC Role explicitly to the designated GitHub repository and production branch.
- Domain Routing: Maintain the default CloudFront URL as an active fallback for demonstration purposes if DNS propagation stalls.

*Contingency Planning*

- If public domain routing is delayed, default back to using the native CloudFront URL.
- If WAF rules unexpectedly block valid client actions, flip rules to Count mode or disable them temporarily.
- If the CI/CD pipeline breaks, execute emergency manual overrides using the AWS SAM CLI and native CLI commands.
- If ZaloPay webhooks fail to update states, query CloudWatch Logs and manually patch the transaction state inside DynamoDB if required.
- If old frontend assets persist, trigger an immediate manual CloudFront Cache Invalidation.

### 8. Expected Outcomes

*Technical Improvements* The completed project yields a fully realized serverless e-commerce platform encompassing every core architectural tier: frontend hosting, backend business APIs, robust authentication, reliable NoSQL databases, media upload handles, secure third-party payment settlement, scheduled jobs, strict perimeter security, and automated delivery pipelines.

*Educational Outcomes* The developer acquires practical engineering skills in orchestrating diverse cloud components into a cohesive application ecosystem using Route 53, WAF, CloudFront, S3, Cognito, API Gateway, Lambda, DynamoDB, EventBridge, CloudWatch, SNS, IAM, and CloudFormation.

*Long-Term Value* The foundational architecture acts as a production-ready baseline that can be enhanced with specialized apex custom domains, custom SSL certificates managed via ACM, business analytics dashboards, fulfillment logistic interfaces, secondary payment channels, item recommendation systems, and separate staging/production environments.