# AWS Cloud Portfolio Website

A personal portfolio website built with HTML and CSS,
stored in a private Amazon S3 bucket, and delivered
over HTTPS through Amazon CloudFront.

## Live Website

https://d36fitrw1zr5sn.cloudfront.net

## Technologies Used

- HTML and CSS
- GitHub for source control
- Amazon S3 for file storage
- Amazon CloudFront for content delivery
- CloudFront Origin Access Control (OAC)

## Architecture

1. A visitor requests the website through CloudFront.
2. CloudFront serves cached content or retrieves it from S3.
3. OAC authenticates CloudFront's requests to the private bucket.

## Configuration

- S3 bucket: ken-cloud-portfolio-121205
- S3 Region: us-east-1 (N. Virginia)
- S3 Block Public Access: enabled
- S3 encryption: SSE-S3
- CloudFront default root object: index.html
- Viewer protocol policy: Redirect HTTP to HTTPS

## Tests Completed

- [x] Previewed the website locally.
- [x] Checked navigation and narrow-screen layout locally.
- [x] Confirmed the live website loads through CloudFront.
- [x] Confirmed the HTTPS redirect setting.
- [x] Confirmed the direct S3 object URL returns Access Denied
      without AWS authentication.

## What I Learned

- How to store website files in S3.
- How CloudFront delivers content from an S3 origin.
- How OAC allows access without making the bucket public.
- Why the default root object matters.
- How to verify HTTPS settings and private origin access.

## Next Improvements

- Practice updating the deployed website and its cache.
- Add my resume and professional links.
- Document deployment and cleanup procedures.
