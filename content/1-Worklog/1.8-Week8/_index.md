---
title: "Week 8 Worklog"
date: 2026-06-06
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Week 8 Objectives:

- Integrate authentication and authorization using Amazon Cognito.

### Tasks to be deployed this week:

| Day | Task                                                                                                                                    | Start Date | Completion Date | Reference Material |
| --- | --------------------------------------------------------------------------------------------------------------------------------------- | ---------- | --------------- | ------------------ |
| 2   | - Configure Cognito Customer User Pool to allow customers to log in, place orders, and view order history.                              | 08/06/2026 | 08/06/2026      |                    |
| 3   | - Configure Cognito Admin User Pool to allow administrators to log in and manage the system.                                            | 09/06/2026 | 09/06/2026      |                    |
| 4   | - Integrate Cognito login into the frontend. After successful login, the frontend receives a JWT token and stores it to make API calls. | 10/06/2026 | 10/06/2026      |                    |
| 5   | - Secure critical APIs using tokens. Differentiate customer and admin flows, and handle cases with missing or invalid tokens.           | 11/06/2026 | 11/06/2026      |                    |
| 6   | - Test customer and admin authentication. Verify that customers can place orders and admins can manage products and orders.             | 12/06/2026 | 12/06/2026      |                    |

### Achievements for Week 8:

- The system now features functional authentication and basic role-based authorization separating customers and administrators.
