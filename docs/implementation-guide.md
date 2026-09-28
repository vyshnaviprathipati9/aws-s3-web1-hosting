# AWS S3 Static Website Hosting - Implementation Guide

# Overview

This guide explains the complete implementation process of hosting a static website using Amazon S3.

The objective is to understand how Amazon S3 can be used as a web hosting service while learning AWS security concepts such as bucket policies, public access configuration, and IP-based access restrictions.

---

# Prerequisites

Before starting this project, ensure you have:

- An AWS Account
- IAM User with Amazon S3 permissions
- Basic HTML knowledge
- A web browser
- Internet connection

---

# Step 1 - Create an S3 Bucket

Navigate to:

AWS Console → Amazon S3 → Create Bucket

Bucket Name:

```
brewnote-srinivas-cloud
```

Choose Region:

```
Asia Pacific (Mumbai)
```

Leave the remaining settings as default and create the bucket.

---

# Step 2 - Upload Website Files

Prepare two HTML files:

- index.html
- error.html

Upload both files into the bucket.

---

# Step 3 - Enable Static Website Hosting

Navigate to:

Bucket → Properties

Scroll to:

Static Website Hosting

Enable:

```
Enable
```

Index Document:

```
index.html
```

Error Document:

```
error.html
```

Save the configuration.

---

# Step 4 - Configure Public Access

Go to:

Permissions

Edit Block Public Access settings.

Disable:

```
Block All Public Access
```

Acknowledge the warning and save.

---

# Step 5 - Configure Bucket Policy

Apply the following bucket policy:

```json
{
  "Version":"2012-10-17",
  "Statement":[
    {
      "Sid":"PublicRead",
      "Effect":"Allow",
      "Principal":"*",
      "Action":"s3:GetObject",
      "Resource":"arn:aws:s3:::brewnote-srinivas-cloud/*"
    }
  ]
}
```

Save the policy.

---

# Step 6 - Test Website

Open the Website Endpoint.

Expected Result:

Home page loads successfully.

---

# Step 7 - Test Error Page

Visit:

```
website-endpoint/abc.html
```

Expected Result:

Custom 404 Error Page appears.

---

# Step 8 - Restrict Website Access

Identify your public IP address.

Modify the bucket policy to allow access only from that IP.

Verify:

- Allowed IP → Website loads.
- Different IP → Access Denied.

---

# Cleanup

Delete:

- Objects
- Bucket
- Bucket Policy

This prevents unnecessary AWS charges.

---

# Troubleshooting

## 403 Forbidden

Cause:

Bucket Policy missing or incorrect.

Solution:

Verify:

- Public Access
- Bucket Policy
- Website Hosting

---

## 404 Error

Cause:

Incorrect Index or Error Document.

Solution:

Verify file names.

---

## Access Denied

Cause:

IP Restriction.

Solution:

Update bucket policy with your current public IP.

---

# Best Practices

- Follow least privilege.
- Avoid public buckets in production.
- Enable logging.
- Use CloudFront.
- Use HTTPS.
- Use IAM roles.
- Monitor using CloudWatch.

---

# Learning Summary

After completing this project, you should understand:

- Amazon S3
- Buckets
- Objects
- Static Website Hosting
- Bucket Policies
- Public Access
- Website Endpoints
- Security
- Access Control
- IP Restriction