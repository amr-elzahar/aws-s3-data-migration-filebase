# S3 to Filebase Sync Workflow

This repository contains a GitHub Actions workflow to sync data from an AWS S3 bucket to a Filebase bucket using `rclone` utility.

## Workflow Description

The workflow is triggered to sync data every hour. It performs the following steps:

1. **Install Rclone**
2. **Checkout Repository**
3. **Inject Access Keys Into Rclone Conf File**
4. **Run rclone Sync**

## Prerequisites

1. **GitHub Secrets**: Ensure the following secrets are added to your GitHub repository:
   - `AWS_ACCESS_KEY_ID`
   - `AWS_SECRET_ACCESS_KEY`
   - `FILEBASE_ACCESS_KEY_ID`
   - `FILEBASE_SECRET_ACCESS_KEY`

### s3source

- **Type**: `s3`
- **Provider**: `AWS`
- **Region**: `us-east-1`

### filebasedestination

- **Type**: `s3`
- **Provider**: `Other`
- **Endpoint**: `https://s3.filebase.com`
- **Region**: `us-east-1`
