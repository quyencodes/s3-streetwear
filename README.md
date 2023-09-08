# MidiPlayerJS

## Tech Stack

<div align="left" width="100%">
  <img src="https://img.shields.io/badge/Amazon%20AWS-232F3E.svg?style=for-the-badge&logo=Amazon-AWS&logoColor=white" alt="AWS Badge"/>
</div>

## Project Description 📝

The

## Getting Started 🧑‍🍳

1. Fork and clone the repository:
   ```bash
   $ git clone https://github.com/quyencodes/s3-streetwear.git
   ```
2. Create an AWS S3 bucket here: https://aws.amazon.com/s3/
3. For the AWS S3 Survey, go with the default settings for the most part. Except these two options
   - Object Ownership: ACLs Enabled with Bucket Owner preferred
   - Block Public Access settings for this bucket: Uncheck Block all public access. We want to access this data publicly
4. Search for the S3 bucket you just created and upload your repo/files to the S3 bucket
5. Click the file you just uploaded. Click permissions. Enable Object access for public read
6. At this point, when we click the `Object URL` we should be able to see our data on the browser. However, if we want to use the S3 bucket in a data driven way, we might run into a CORS error
7. Please navigate to your bucket -> permissions -> Edit cross-origin resource sharing (CORS) and add the following JSON object

```json
[
  {
    "AllowedHeaders": ["*"],
    "AllowedMethods": ["GET", "PUT", "POST", "DELETE"],
    "AllowedOrigins": ["*"],
    "ExposeHeaders": [
      "x-amz-server-side-encryption",
      "x-amz-request-id",
      "x-amz-id-2"
    ],
    "MaxAgeSeconds": 3000
  }
]
```

8. Great, you should be able to access the S3 bucket via an API request. If you cannot, here are some resources:

- <a href="https://repost.aws/knowledge-center/read-access-objects-s3-bucket" rel="noopener noreferrer">https://repost.aws/knowledge-center/read-access-objects-s3-bucket</a>
- <a href="https://docs.aws.amazon.com/AmazonS3/latest/userguide/about-object-ownership.html?icmpid=docs_amazons3_console" rel="noopener noreferrer">https://docs.aws.amazon.com/AmazonS3/latest/userguide/about-object-ownership.html?icmpid=docs_amazons3_console</a>
- <a href="https://www.youtube.com/watch?v=dRHqGTOI3Ik" rel="noopener noreferrer">https://www.youtube.com/watch?v=dRHqGTOI3Ik</a>
