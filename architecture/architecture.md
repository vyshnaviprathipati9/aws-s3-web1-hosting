# AWS Architecture

```
        User
          │
          ▼
   Web Browser
          │
          ▼
 Amazon S3 Bucket
          │
 ┌────────┴────────┐
 ▼                 ▼
index.html     error.html
```

## Components

### User

The person accessing the website.

### Browser

Sends an HTTP request.

### Amazon S3

Stores and serves static files.

### index.html

Main webpage displayed to users.

### error.html

Custom page shown when a requested page is unavailable.