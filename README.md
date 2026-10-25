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

## Updating the Website

1. Edit index.html in GitHub.
2. Commit the changes with a descriptive message.
3. Download the updated file, keeping its name as index.html.
4. Upload it to the existing S3 bucket, replacing index.html.
5. Open the CloudFront distribution's Invalidations tab.
6. Create an invalidation using the path /*.
7. Wait for the invalidation to complete.
8. Open the CloudFront HTTPS address in a fresh private window.
9. Verify the updated content appears.

Successfully tested by publishing the "Live on AWS" project update.

## Deployment Summary

1. Create a general-purpose S3 bucket in us-east-1.
2. Keep Block Public Access enabled and ACLs disabled.
3. Use SSE-S3 encryption.
4. Upload index.html to the bucket root.
5. Create a CloudFront distribution using the S3 bucket as its origin.
6. Use Origin Access Control and grant the distribution read access
   through the S3 bucket policy.
7. Set the default root object to index.html.
8. Set the viewer protocol policy to Redirect HTTP to HTTPS.
9. Verify CloudFront access works and anonymous S3 access is denied.

## Cleanup Plan — Not Executed

The website remains running as my portfolio.

If retiring this project:
1. Preserve the website source and documentation in GitHub.
2. Disable the CloudFront distribution.
3. Wait for the disabling update to finish deploying.
4. Delete the CloudFront distribution.
5. Delete its OAC if no other distribution uses it.
6. Empty the project S3 bucket, then delete the bucket.
7. Review billing after usage data updates for any remaining costs.

## Next Improvements

- Add my resume and professional links.
- Add more completed projects.
- Add an architecture diagram.
