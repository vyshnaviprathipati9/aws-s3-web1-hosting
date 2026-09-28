# Troubleshooting Guide

## Problem 1: 403 Forbidden

### Possible Causes

- Bucket Policy not configured
- Public Access still blocked
- Incorrect bucket ARN

### Solution

- Verify bucket policy
- Disable Block Public Access
- Check bucket name

---

## Problem 2: 404 Not Found

### Possible Causes

- Missing index.html
- Wrong Error Document
- File upload failed

### Solution

Re-upload the files.

---

## Problem 3: Access Denied after IP Restriction

### Cause

Public IP address changed.

### Solution

Update the SourceIp value in the bucket policy.

---

## Problem 4: Website Not Updating

### Cause

Browser cache.

### Solution

Use:

Ctrl + Shift + R

or

Open the page in Incognito Mode.