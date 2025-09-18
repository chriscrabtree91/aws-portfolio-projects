# Project – Hosting justcallchrisok.com with AWS S3 + Route 53 + CloudFront

## Overview

This project demonstrates the complete deployment of a professional static website (**[https://justcallchrisok.com](https://justcallchrisok.com)**) using Amazon Web Services. It showcases domain management via **Porkbun**, email routing via **Zoho Mail**, and hosting through a combination of **S3**, **CloudFront**, and **Route 53**. The goal was to fully deploy a secure, performant, custom-branded website with HTTPS and professional email.

---

## Architecture

![Architecture Diagram](screenshots/architecture-diagram.png)

---

## Steps I Took

### 1. Purchased and Configured the Domain

* Domain: `justcallchrisok.com` was purchased through **Porkbun**
* Accessed DNS management via Porkbun dashboard
* Updated nameservers to point to **AWS Route 53**

### 2. Set Up Professional Email (Zoho Mail)

* Created Zoho Mail account
* Set up domain: `justcallchrisok.com`
* Verified domain ownership using TXT records in Porkbun
* Added MX, SPF, DKIM, and CNAME records in Porkbun

  * Email: `service@justcallchrisok.com`
  * Ensured DNS propagation and tested email functionality

### 3. Created and Configured S3 Bucket

* Bucket name: `justcallchrisok.com`
* Unchecked **"Block all public access"**
* Enabled **Static website hosting** with:

  * Index document: `index.html`
  * Error document: `404.html`
* Uploaded the static website files (HTML, CSS, assets)

### 4. Set S3 Bucket Policy for Public Access

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::justcallchrisok.com/*"
    }
  ]
}
```

### 5. Configured Route 53 DNS Zone

* Created **Hosted Zone** in Route 53 for `justcallchrisok.com`
* Added A record using **Alias to CloudFront** distribution
* Verified record propagation

### 6. Created CloudFront Distribution for HTTPS and Caching

* Set S3 bucket as origin
* Enabled redirect HTTP to HTTPS
* Attached an **SSL certificate** via AWS Certificate Manager
* Added custom domain `justcallchrisok.com` to alternate CNAMEs
* Deployed distribution and copied the CloudFront domain

### 7. Final DNS Setup in Route 53

* Created an **A record (alias)** for the domain pointing to the CloudFront distribution
* Site became live and accessible via HTTPS:
  [https://justcallchrisok.com](https://justcallchrisok.com)

---

## Screenshots

**Porkbun DNS Management Panel**
![DNS Settings](screenshots/porkbun-dns.png)

**Zoho DNS Setup for Email**
![Zoho Email Setup](screenshots/zoho-dns.png)

**S3 Bucket Properties & Static Hosting**
![S3 Setup](screenshots/s3-hosting.png)

**S3 Bucket Policy**
![Bucket Policy](screenshots/bucket-policy.png)

**Uploaded Website Files in S3**
![S3 Contents](screenshots/s3-contents.png)

**CloudFront Distribution Settings**
![CloudFront](screenshots/cloudfront.png)

**Route 53 Hosted Zone Records**
![Route 53 Records](screenshots/route53.png)

**Live Website Preview**
![Site Screenshot](screenshots/live-preview.png)

---

## Cost

* Domain via Porkbun: \~\$10/year
* AWS S3 Storage: \~\$0 (Free Tier)
* CloudFront (low usage): \$0 – \$1/month
* Route 53 Hosted Zone: \$0.50/month
* Zoho Mail: \~\$1/month (paid basic tier)

**Total: Less than \$2/month to host a secure, branded business website with professional email.**
