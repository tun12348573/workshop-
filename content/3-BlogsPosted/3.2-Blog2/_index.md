---
title: "Blog 2"
date: 2026-07-06
weight: 2
chapter: false
pre: " <b> 3.2. </b> "
---

# AUTOMATED EXTRACTION OF COMPRESSED FILES ON AMAZON S3 USING AWS BATCH AND AMAZON ECS

While learning about AWS Batch, I read the article **"Automated extraction of compressed files on Amazon S3 using AWS Batch and Amazon ECS"** on the AWS Storage Blog.

What impressed me the most about this solution was its ability to build a fully automated data processing workflow using an **event-driven architecture**. When a compressed file is uploaded to Amazon S3, the system automatically triggers AWS Batch to run a container, process the file, extract the content, and upload the result back to S3.

Instead of maintaining an EC2 server that runs continuously to monitor and extract files, this architecture only creates compute resources when there is actual work to process. This approach helps optimize cost and reduces infrastructure management effort.

## 1. Problem Statement

Assume that a company regularly receives data from multiple partners. These partners upload large compressed files such as `.tar` files to Amazon S3.

Each file may contain thousands of images, documents, or data files that need to be processed.

Example:

```text
backup.tar
├── image01.jpg
├── image02.jpg
├── image03.jpg
├── report.csv
└── ...
```

However, downstream systems often can only process individual files instead of directly processing the entire TAR file. Therefore, an intermediate step is needed to:

- Detect when a new file is uploaded.
- Extract the compressed file.
- Upload the extracted files back to Amazon S3.
- Allow other systems to continue processing the data.

If this is implemented using a traditional approach, an EC2 instance may need to run continuously to monitor the bucket and extract files. This approach increases cost and requires manual server management.

## 2. Overall Architecture

Based on my understanding, the architecture works as follows:

```text
Upload TAR File
   ↓
Amazon S3
   ↓
Amazon EventBridge
   ↓
AWS Batch
   ↓
Amazon ECS Container
   ↓
Download → Extract → Upload
   ↓
Amazon S3 Output
```

The key point is that no server runs continuously. When there is no new file, the system does not consume compute resources.

<img src="/workshop-/images/3-BlogsPosted/blog2-s3-batch-ecs.png" alt="Automated File Extraction Architecture" style="max-width: 100%; height: auto;">

## 3. Role of Each Service

### Amazon S3

Amazon S3 is used to store both input and output data. When a user uploads a TAR file to the bucket, S3 generates an Object Created event. After the extraction process is completed, the output files are uploaded back to S3.

### Amazon EventBridge

Amazon EventBridge acts as the event coordinator. It listens for events from Amazon S3 and, when a new file is uploaded, sends a request to create an AWS Batch Job.

### AWS Batch

AWS Batch is responsible for managing the batch processing job. It receives the processing request, selects suitable compute resources, starts the container runtime environment, and releases the resources after the job is completed.

One thing I learned is that AWS Batch is not only useful for Machine Learning or High Performance Computing. It is also very suitable for batch data processing workloads.

### Amazon ECS

AWS Batch runs the processing logic through a container on Amazon ECS. The container performs the following steps:

- Download the file from S3.
- Extract the compressed file.
- Upload the extracted result back to S3.

Packaging the processing logic inside a Docker container makes the workflow easier to maintain, update, and scale.

### Amazon EBS

The container does not extract the file directly on S3. Instead, the TAR file is downloaded to temporary storage such as Amazon EBS. The processing flow is:

1. Download the TAR file from S3 to EBS.
2. Extract the file on EBS.
3. Upload the extracted files back to S3.
4. Release the resources after the Batch Job finishes.

## 4. Workflow

The system works through the following steps:

1. A user uploads a TAR file to Amazon S3.
2. Amazon S3 generates an Object Created event.
3. Amazon EventBridge receives the event.
4. EventBridge sends a request to create an AWS Batch Job.
5. AWS Batch starts the compute environment.
6. AWS Batch runs a container through Amazon ECS.
7. The container downloads the TAR file from S3.
8. The file is extracted on temporary storage.
9. The extracted files are uploaded back to Amazon S3.
10. The Batch Job ends and the resources are released.

## 5. Why Use AWS Batch Instead of AWS Lambda?

At first, I also wondered why AWS Lambda was not used for this problem.

After learning more, I realized that the main reasons are data size and processing time. In real-world scenarios, TAR files can be very large, even tens or hundreds of GB. With this amount of data, Lambda may face limitations such as:

- Execution time limit.
- Temporary storage limit.
- CPU and memory limitations.
- Difficulty handling long-running workloads.

Meanwhile, AWS Batch can choose suitable compute resources, run containers, and process large workloads more flexibly.

Therefore, AWS Batch is more suitable for batch data processing tasks that involve large files or long processing time.

## 6. What I Learned

After reading the blog, I learned several important points.

First, not every file processing problem should use Lambda. For large workloads or long-running tasks, AWS Batch is a more suitable choice.

Second, an event-driven architecture helps the system consume compute resources only when new data needs to be processed. This helps reduce operational cost.

Third, packaging processing logic in a Docker container makes the system easier to maintain and extend.

In my opinion, this architecture is not only suitable for file extraction. It can also be applied to many other use cases, such as:

- Batch image resizing.
- Video format conversion.
- CSV to Parquet conversion.
- Log analysis.
- Document OCR.
- AI Batch Inference.
- ETL Pipeline.

## 7. Conclusion

Through this blog, I gained a better understanding of how Amazon S3, Amazon EventBridge, AWS Batch, and Amazon ECS can be combined to build an automated data processing pipeline.

The most valuable points of this architecture are cost optimization through the pay-as-you-go model, flexible scalability, and reduced infrastructure management effort.

In the future, I would like to try implementing this architecture step by step to better understand how AWS services work together in a real-world data processing system.

## 8. References

- AWS Storage Blog: Automated extraction of compressed files on Amazon S3 using AWS Batch and Amazon ECS
- Amazon S3 Documentation
- Amazon EventBridge Documentation
- AWS Batch Documentation
- Amazon ECS Documentation
- Amazon EBS Documentation
