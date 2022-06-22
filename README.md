# Overview

This project, joshkautz.com, is a static site to serve as a personal portfolio and branding website. It's simply a collection of links to social media platforms to increase hireability.

# Deployment (New)

This is used now that I am hosting via Firebase Hosting.

## Manual - [Firebase CLI](https://firebase.google.com/docs/cli)

### Deploy to Firebase Hosting Preview Channel

Windows
```PowerShell
$Date = Get-Date -Format "dddd-MM-dd-yyyy-HH-mm-ss"
$Channel = "Preview-" + $Date
firebase hosting:channel:deploy $Channel --expires 1d --project josh-kautz --json
```

Linux
```Bash
Date=$(date +'%A-%m-%d-%Y-%H-%M-%S')
Channel="Preview-"$Date
firebase hosting:channel:deploy $Channel --expires 1d --project josh-kautz --json
```

### Deploy to Firebase Hosting Live Channel
Windows
```PowerShell
firebase deploy --only hosting --project josh-kautz --json
```

Linux
```Bash
firebase deploy --only hosting --project josh-kautz --json
```

## Automatic - [Firebase Hosting GitHub Action](https://github.com/marketplace/actions/deploy-to-firebase-hosting)

1. Create a Pull Request to merge new feature branch into the Main branch.
2. Firebase Hosting GitHub Action will build and deploy the new changes to a Preview Channel on Firebase Hosting.
3. After testing the features at the Preview Channel URL, merge the Pull Request into the Main branch.
4. Firebase Hosting GitHub Action will build and deploy the new changes to the Live Channel on Firebase Hosting.

# Deployment (Old)

This was used when I was hosting on AWS S3 and serving via AWS CloudFront.

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