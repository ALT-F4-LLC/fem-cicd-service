# Cloud CI/CD with GitHub Actions Course

This is a companion repo for the [Master.dev Cloud CI/CD with GitHub Actions course](https://master.dev/courses/github-actions/)

## Pre-requisites for this course

- GitHub account (free plan is fine)
- AWS account on the free tier with admin access
- Node (v22) installed locally

## Reference branches

The course starts from scratch with an empty repo and is divided into three phases: POC, Stable, and Enterprise. Reference branches in this repo contains the final state of each phase:

- Proof-of-concept end state -> `git checkout poc`
- Stable end state -> `git checkout stable`
- Enterprise end state -> `git checkout enterprise`

## POC Phase Bucket Permissions
During the POC Phase, S3 bucket permissions are configured with a JSON object. Under the "Permissions" tab for your bucket, edit the `Block public access` setting so it's turned off. Then copy/paste the JSON below

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::YOUR-BUCKET-NAME/*"
        }
    ]
}
```
