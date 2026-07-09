---
title: "Week 11 Worklog"
date: 2026-06-29
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Week 11 Objectives:

- Build background tasks, monitoring, and alerting for the system.

### Tasks to be deployed this week:

| Day | Task                                                                                                                                                  | Start Date | Completion Date | Reference Material |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | --------------- | ------------------ |
| 2   | - Build PaymentExpirySchedulerFunction to check for overdue pending orders and automatically update their statuses.                                   | 29/06/2026 | 29/06/2026      |                    |
| 3   | - Configure EventBridge to trigger PaymentExpirySchedulerFunction on a schedule. Verify that the Lambda executes automatically without user requests. | 30/06/2026 | 30/06/2026      |                    |
| 4   | - Build RefundReconciliationFunction to reconcile refund statuses with ZaloPay and update the corresponding data records.                             | 01/07/2026 | 01/07/2026      |                    |
| 5   | - Configure CloudWatch Logs and Metrics for Lambda, API Gateway, and background functions. Inspect logs to troubleshoot errors.                       | 02/07/2026 | 02/07/2026      |                    |
| 6   | - Configure CloudWatch Alarms and SNS Topics. Confirm the email subscription to receive automated alerts whenever system errors occur.                | 03/07/2026 | 03/07/2026      |                    |

### Achievements for Week 11:

- The system now includes scheduled jobs, centralized logging, system monitoring, and email alerting capabilities to support operations.
