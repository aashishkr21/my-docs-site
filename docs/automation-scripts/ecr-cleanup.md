# AWS ECR Image Cleanup Script

## Overview
This Python script automates the cleanup of old Docker images stored in AWS Elastic Container Registry (ECR). It helps in managing storage costs and maintaining a clean repository by deleting images older than a specified number of days.

## Prerequisites
- Python 3 installed
- AWS CLI configured with the appropriate credentials
- Boto3 installed (`pip install boto3`)

## Configuration
Modify the following parameters in the script as per your requirements:
- **`REGION`**: AWS region where your ECR repository is located
- **`REPO_NAME`**: Name of the ECR repository
- **`DAYS_THRESHOLD`**: Number of days beyond which images should be deleted

## Installation
1. Ensure you have Python and required dependencies installed.
2. Install dependencies:
   ```sh
   pip install boto3
   ```

## Usage
Run the script using:
```sh
python cleanup_ecr_images.py
```

## AWS Permissions
Ensure that the IAM user or role executing the script has the following permissions:
```json
{
    "Effect": "Allow",
    "Action": [
        "ecr:DescribeImages",
        "ecr:BatchDeleteImage"
    ],
    "Resource": "*"
}
```

## Notes
- This script **permanently deletes** Docker images from AWS ECR. Double-check before running it in a production environment.
- Consider testing in a non-production AWS account before applying it to a live setup.

## License
MIT License


