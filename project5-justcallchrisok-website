# JustCallChrisOK.com — Static Website Deployment (AWS + Porkbun + Zoho Mail)

This project showcases the complete deployment of a live static website at [https://justcallchrisok.com](https://justcallchrisok.com), utilizing AWS infrastructure and a custom domain with business email integration.

---

## 🛠️ Tech Stack

| Service       | Purpose                         |
|---------------|----------------------------------|
| AWS S3        | Static website hosting           |
| AWS CloudFront| CDN and SSL (HTTPS)              |
| Porkbun       | Domain registrar + DNS settings  |
| Zoho Mail     | Business email hosting           |
| HTML/CSS      | Static content design            |

---

## 🌐 Domain Setup via Porkbun

The domain `justcallchrisok.com` was registered through Porkbun, with DNS records configured to support AWS services and Zoho Mail.

**Steps Completed:**
- Registered domain through Porkbun.
- Added DNS records for:
  - AWS SSL certificate validation.
  - CloudFront routing (ALIAS and CNAME).
  - Zoho Mail (MX, SPF, DKIM, DMARC).

> 🖼️ Screenshot: Porkbun DNS record configuration

---

## 📩 Zoho Mail Configuration

Custom domain email was configured using Zoho Mail.

**Steps Completed:**
- Domain verified in Zoho with TXT record.
- MX records pointed to Zoho servers.
- SPF, DKIM, and DMARC records added for authentication.
- Final email address: `service@justcallchrisok.com`

> 🖼️ Screenshot: Zoho domain verification  
> 🖼️ Screenshot: DNS records for email (MX, SPF, DKIM, DMARC)

---

## ☁️ AWS S3 Static Hosting

An S3 bucket was created to host the static HTML/CSS website.

**Steps Completed:**
- Bucket named `justcallchrisok.com` created in us-east-1.
- Static website hosting enabled.
- `index.html` uploaded and configured as root document.
- Bucket policy updated for public access.

> 🖼️ Screenshot: S3 static hosting configuration  
> 🖼️ Screenshot: Bucket policy  
> 🖼️ Screenshot: File upload view

---

## 🔒 SSL Certificate with ACM

An SSL certificate was issued via AWS Certificate Manager.

**Steps Completed:**
- Requested certificate for `justcallchrisok.com` and `www.justcallchrisok.com`.
- DNS validation performed through Porkbun CNAME record.
- Certificate issued and ready for CloudFront.

> 🖼️ Screenshot: ACM issued certificate  
> 🖼️ Screenshot: DNS validation record

---

## 🚀 CloudFront CDN + HTTPS

CloudFront was configured to serve the S3 website securely over HTTPS.

**Steps Completed:**
- CloudFront distribution created.
- Origin domain: S3 static site URL.
- Alternate domain names added (`www` and apex).
- SSL certificate attached from ACM.
- HTTP traffic redirected to HTTPS.

> 🖼️ Screenshot: CloudFront settings and domain setup

---

## 🌍 DNS Routing

Porkbun DNS was updated to route traffic to CloudFront.

**Steps Completed:**
- ALIAS record set for `justcallchrisok.com` → CloudFront URL.
- CNAME record set for `www.justcallchrisok.com` → CloudFront.

> 🖼️ Screenshot: Final DNS records pointing to CloudFront

---

## ✅ Website Live

The site is now accessible at [https://justcallchrisok.com](https://justcallchrisok.com) with HTTPS enabled and all email services functioning.

> 🖼️ Screenshot: Browser showing live site  
> 🖼️ Screenshot: Verified status in Zoho and AWS

---

## 📸 Screenshot Reference Guide

| Section                    | Screenshot Title                            |
|----------------------------|---------------------------------------------|
| Domain Setup               | Porkbun DNS configuration                   |
| Zoho Mail                  | Zoho domain + MX/SPF/DKIM/DMARC records     |
| S3 Static Hosting          | S3 bucket config + public access + files    |
| SSL Certificate (ACM)      | ACM issued cert + validation CNAME          |
| CloudFront Distribution    | CloudFront settings                         |
| DNS to CloudFront          | Porkbun ALIAS and CNAME setup               |
| Final Confirmation         | Live site + Zoho/AWS SES status             |
