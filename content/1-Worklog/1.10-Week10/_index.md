---
title: "Week 10 Worklog"
date: 2026-06-22
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Week 10 Objectives:

- Finalize product image uploading and integrate ZaloPay payment gateway.

### Tasks to be deployed this week:

| Day | Task                                                                                                                                                             | Start Date | Completion Date | Reference Material |
| --- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | --------------- | ------------------ |
| 2   | - Create a dedicated S3 Product Images Bucket to store product images, keeping it completely separate from the frontend bucket.                                  | 22/06/2026 | 22/06/2026      |                    |
| 3   | - Build an API to generate S3 presigned URLs, enabling the admin browser to upload images directly to S3.                                                        | 23/06/2026 | 23/06/2026      |                    |
| 4   | - Integrate image uploading into the admin dashboard. Verify image uploads, save image URLs to products, and display images on the website.                      | 24/06/2026 | 24/06/2026      |                    |
| 5   | - Integrate ZaloPay Sandbox. Research payment creation flow, user redirection, and handling callbacks.                                                           | 25/06/2026 | 25/06/2026      |                    |
| 6   | - Finalize the core payment flow. Lambda generates payment requests, ZaloPay sends callbacks back to API Gateway, and Lambda updates order statuses in DynamoDB. | 26/06/2026 | 26/06/2026      |                    |

### Achievements for Week 10:

- Admins can successfully upload product images via S3 presigned URLs, and the system features a functional, basic ZaloPay Sandbox payment flow.
