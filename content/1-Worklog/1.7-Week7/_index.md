---
title: "Week 7 Worklog"
date: 2026-06-01
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Week 7 Objectives:

- Design the database and integrate DynamoDB into the backend.

### Tasks to be deployed this week:

| Day | Task                                                                                                                                           | Start Date | Completion Date | Reference Material |
| --- | ---------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | --------------- | ------------------ |
| 2   | - Design the Products table in DynamoDB to store product names, descriptions, prices, images, stock levels, and visibility status.             | 01/06/2026 | 01/06/2026      |                    |
| 3   | - Design the Orders table to store order information, customer details, purchased items, total amounts, payment status, and processing status. | 02/06/2026 | 02/06/2026      |                    |
| 4   | - Integrate Lambda with DynamoDB for the product API group, replacing mock data with real data from DynamoDB.                                  | 03/06/2026 | 03/06/2026      |                    |
| 5   | - Integrate Lambda with DynamoDB for the order API group, handling order creation, status updates, and inventory changes.                      | 04/06/2026 | 04/06/2026      |                    |
| 6   | - Test the end-to-end data flow between frontend, API Gateway, Lambda, and DynamoDB. Debug IAM permissions, data formatting, and queries.      | 05/06/2026 | 05/06/2026      |                    |

### Achievements for Week 7:

- DynamoDB is fully operational with Products and Orders tables, enabling the backend to read and write live data on AWS.
