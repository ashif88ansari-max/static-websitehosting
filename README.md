 # Static Website Hosting on Amazon S3

A beginner-friendly cloud project that demonstrates hosting a static HTML website using **Amazon S3**, with GitHub used for source control and documentation.

## Project status

- [x] Website source (`index.html`) created
- [x] Project documentation created
- [x] S3 bucket created and configured
- [x] Website files uploaded to S3
- [x] Static website hosting enabled
- [x] Website endpoint tested

**Important:** Uploading this repository to GitHub does not deploy it to AWS. Complete the AWS steps below when your AWS account is accessible. Do not claim the website is live until the endpoint has been tested.

## Architecture

```text
Visitor's browser
       |
       v
S3 static website endpoint
       |
       v
Amazon S3 bucket
       |
       +-- index.html
```

GitHub stores the project source and documentation; it is not the AWS hosting service in this project.

## Files

| File | Purpose |
|---|---|
| `index.html` | Responsive static website |
| `README.md` | Project overview and deployment guide |
| `bucket-policy-template.json` | Example read-only bucket policy template |

## Deployment steps

1. Sign in to the AWS Management Console and open **Amazon S3**.
2. Create a general purpose bucket. Bucket names must be globally unique.
3. Open the bucket and upload `index.html`.
4. Open **Properties** → **Static website hosting** → **Edit**.
5. Choose **Enable**, select **Host a static website**, and set the index document to `index.html`.
6. Save changes.
7. If the site must be publicly accessible, review S3 Block Public Access settings and allow only the access needed for this bucket. Then add a read-only bucket policy using your exact bucket name.
8. Open the **Bucket website endpoint** shown in the Static website hosting section and test the page.

## Security and cost notes

- Never upload AWS access keys, passwords, PAN/Aadhaar details, private files, or other secrets to GitHub or a public S3 bucket.
- A public website bucket allows visitors to read objects. Keep only public website assets in it.
- Use least privilege. The policy template grants `s3:GetObject` only; it does not grant upload, delete, or bucket administration.
- S3 storage and requests may incur charges. Remove test resources you no longer need.
- The S3 static website endpoint uses HTTP. For HTTPS and a production setup, consider CloudFront in front of S3 with an appropriate origin access configuration.

## Testing checklist

- [x] `index.html` exists in the bucket root.
- [x] Static website hosting is enabled.
- [x] Index document is exactly `index.html`.
- [x] Public read access is configured only if intended.
- [x] Website endpoint loads successfully.
- [x] No private information is exposed.

## Learning outcomes

- Understand S3 buckets and objects.
- Understand static website hosting.
- Practice uploading website assets.
- Learn basic public-read permissions and least privilege.
- Document a cloud deployment in GitHub.

## Author

Add your name and project completion date here.
