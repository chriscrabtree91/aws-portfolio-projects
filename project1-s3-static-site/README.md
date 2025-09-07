# Project 1 – Static Website Hosting on AWS S3

## Overview
This project demonstrates how I hosted a static website using Amazon S3. The site includes a simple index page and a custom error page. The goal was to show how to configure S3 for static hosting, make the content publicly available, and handle errors cleanly.

---

## Architecture
Browser → S3 Bucket (Static Website Hosting) → index.html / error.html

*(Insert an architecture diagram here when ready.)*

---

## Steps I Took
1. Created an S3 bucket  
   - Name: `ccrabtree-portfolio-site`  
   - Region: `us-east-2` (Ohio)  
   - Turned off “Block all public access” so the bucket could be used for static hosting  

2. Enabled static website hosting in bucket properties  
   - Index document: `index.html`  
   - Error document: `error.html`  

3. Uploaded the website files  
   - `index.html` – basic homepage  
   - `error.html` – 404 page with a link back to home  

4. Added a bucket policy for public read access:
   ```json
   {
     "Version": "2012-10-17",
     "Statement": [
       {
         "Sid": "PublicReadForWebsite",
         "Effect": "Allow",
         "Principal": "*",
         "Action": "s3:GetObject",
         "Resource": "arn:aws:s3:::ccrabtree-portfolio-site/*"
       }
     ]
   }
