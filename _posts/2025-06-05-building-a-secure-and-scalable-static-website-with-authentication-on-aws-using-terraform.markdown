---
layout: post
title: "Building a Secure and Scalable Static Website with Authentication on AWS using Terraform"
date: 2025-06-05
categories: tech
tags: [aws, terraform, static-website, authentication, security, scalability]
author: Etonia Suraki
image: /images/s3_hosted.jpeg
---
                                                                                                                                                                        
In this blog post, I'll walk you through a public repository that deploys a secure and scalable React single-page application (SPA) on AWS, leveraging services like [Amazon S3](https://aws.amazon.com/s3/), [Amazon CloudFront](https://aws.amazon.com/cloudfront/), and [Amazon Cognito](https://aws.amazon.com/cognito/), all orchestrated with [Terraform](https://developer.hashicorp.com/terraform). This solution highlights a robust approach to front-end deployment, incorporating automation, security, and performance best practices.

## The Solution Architecture
The architecture of this solution is designed for efficiency, scalability, and security:

![architecture](../images/s3-cloudfront-architecture.png)

**React Application:** The front-end is a modern React application built with Vite, React, and Tailwind CSS, providing a fast and responsive user experience.
**Amazon S3 for Static Hosting:** The compiled React application is hosted as a static website on an Amazon S3 bucket. S3 provides highly durable, scalable, and cost-effective object storage, ideal for static content.
**Amazon CloudFront for Global Content Delivery:** Amazon CloudFront acts as a content delivery network (CDN), distributing the S3-hosted content globally. This significantly improves load times for users worldwide by caching content at edge locations. CloudFront also provides an extra layer of security and can be configured to enforce HTTPS.
**Amazon Cognito for User Authentication:** User authentication and authorization are handled by Amazon Cognito. This managed service simplifies user sign-up, sign-in, and access control, allowing users to register, receive verification codes, and sign in securely before accessing the main application content. Only authenticated users can access the main page, ensuring data privacy and controlled access.

## Automation with Terraform
Terraform plays a pivotal role in automating the entire infrastructure provisioning and deployment process.

**Infrastructure as Code (IaC):** Terraform defines the entire AWS infrastructure – S3 buckets, CloudFront distributions, Cognito user pools, and their configurations as code. This ensures consistency, repeatability, and version control for your infrastructure.
**Terraform State Management & File locking with S3:** The Terraform state file, which maps real-world resources to your configuration, is securely stored in a designated S3 bucket. To prevent concurrent modifications and ensure state consistency, file locking is implemented with the new S3 capability as of Terraform version 1.9.0, a key aspect for collaborative or automated deployments.

## Streamlined Deployment Workflow
A bash script is integrated into the workflow to manage the frontend application's build and deployment lifecycle:

**Build Process:** The script first builds the React application, optimizing it for production.
**Packaging and Upload:** The built application artifacts are then packaged and uploaded to the designated S3 bucket.
**CloudFront Cache Invalidation:** Crucially, after new content is deployed to S3, the script triggers an invalidation of the CloudFront cache. This ensures that users immediately receive the latest version of the application and are not served stale content from the CDN's cache.

## Key Skills and Technologies Demonstrated

This project showcases a range of valuable skills and technologies:
**- Cloud Computing:** Deep understanding of AWS services including S3, CloudFront, and Cognito.
**- Infrastructure as Code (IaC):** Proficiency in using Terraform for declarative infrastructure provisioning.
**- Front-end Development:** Experience with modern React development using Vite and Tailwind CSS.
**- Security Best Practices:** Utilizing Cognito for authentication and ensuring secure access to application content.
**- Scripting:** Practical application of bash scripting for deployment automation.

## Conclusion
This project serves as a practical example of deploying a secure, scalable, and automated single-page application on AWS. By leveraging Infrastructure as Code with Terraform and integrating key AWS services, the solution provides a robust foundation for modern web applications. Feel free to explore the repository, try it out, and adapt it for your own projects.
You can find the complete code and detailed instructions in the GitHub repository linked below.

GitHub Repository: [kaiviti-adventurer](https://github.com/kaiviti-adventurer/tf-aws-s3-cloudfront-cognito-website)