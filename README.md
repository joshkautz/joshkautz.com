# Overview

This project, joshkautz.com, is a static site to serve as a personal portfolio and branding website. It's simply a collection of links to social media platforms to increase hireability.

# Deploy

## Windows

1. Upload Project to S3 Bucket.
``` PowerShell
aws s3 sync . s3://joshkautz.com/
```

2. Create a new invalidation for the CloudFront distribution.
```PowerShell
aws cloudfront create-invalidation --distribution-id E1ISLD2UYMLZC7 --paths "/*"
```

## Linux

1. Upload Project to S3 Bucket.
``` PowerShell
aws s3 sync . s3://joshkautz.com/
```

2. Create a new invalidation for the CloudFront distribution.
```PowerShell
aws cloudfront create-invalidation --distribution-id E1ISLD2UYMLZC7 --paths "/*"
```