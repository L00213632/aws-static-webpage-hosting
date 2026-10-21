# aws-static-webpage-hosting
<<<<<<< HEAD
https://www.youtube.com/watch?v=oDY5o6sV--Y


## Deploy to Amazon S3

The GitHub Actions workflow at `.github/workflows/deploy-to-s3.yml` syncs the
contents of `website/` to an S3 bucket whenever code is pushed to `main`. You
can also run it manually from the repository's **Actions** tab.

### Configure AWS

1. Create an S3 bucket in the AWS region where you want to host the site.
2. In IAM, ensure the GitHub Actions OIDC identity provider exists for
   `https://token.actions.githubusercontent.com`. Create an IAM role for the
   workflow with a trust policy restricted to this repository and the `main`
   branch. The trust policy should use audience `sts.amazonaws.com` and subject
   `repo:L00213632/aws-static-webpage-hosting:ref:refs/heads/main`.
3. Attach a permissions policy to that role that allows `s3:ListBucket` on your
   bucket and `s3:PutObject` and `s3:DeleteObject` on its objects. The delete
   permission is needed because the workflow uses `aws s3 sync --delete` to
   remove files deleted from the repository.
4. In the GitHub repository, open **Settings > Secrets and variables > Actions
   > Variables** and add:
   - `AWS_ROLE_TO_ASSUME`: the IAM role ARN.
   - `AWS_REGION`: the bucket's AWS region (for example, `eu-west-1`).
   - `AWS_S3_BUCKET`: the bucket name.

The workflow uses short-lived credentials through GitHub OIDC; do not add AWS
access keys to the repository. Configure S3 static website hosting and any
public access or CloudFront settings separately if you want the bucket contents
to be publicly viewable.
>>>>>>> d30299b (Yaml file added to depoy to S3)
>>>>>>
>>>>>>References
>>>>>>
https://www.youtube.com/watch?v=cwX3XAx3CGg&t=38s - CI/CD from GitHub to AWS | Deploy static website from GitHub to S3 | GitHub Actions

https://www.youtube.com/watch?v=sIac8b4njkE - Deploy Static Website on S3 + CloudFront | Automate with CloudFormation

Chatgpt - Model-GPT-6 - Create the YAML file -

>>>>>>   Prompt 1: Create a GitHub Actions YAML file
>>>>>> 
>>>>>>   Prompt 2: Enable S3 static website hosting
>>>>>> 
>>>>>>   Prompt 3: Fix the S3 bucket ARN error
>>>>>> 
>>>>>>   Prompt 4: Troubleshoot the GitHub workflow folder
