## Deployment

Deploy to S3:
```
$ aws s3 sync . s3://joshkautz.com/
```

After making an update, create a new invalidation in the website's CloudFront distribution to immediately have the CloudFront global caches be filled with new the content retrieved from the S3 bucket.