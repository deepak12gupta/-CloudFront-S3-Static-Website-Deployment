# -CloudFront-S3-Static-Website-Deployment

 Project Description
This project demonstrates how to host a fully functional static portfolio website using:
Amazon S3 (for static file storage and hosting)
Amazon CloudFront (for CDN & HTTPS)
Route 53 / Custom Domain (optional for production setup)


✅ Live Site: portfolio.deepakgupta.info
🔐 CloudFront HTTPS Link: https://d16a4uqz2l95pz.cloudfront.net/


🛠️ Services Used and 	Purpose

Amazon S3	Stores and serves static site files

CloudFront	Distributes content with low latency globally

IAM Policies	Controls access permissions

GeoPeeker	Used to verify website availability worldwide


✅ Deployment Steps
Upload Files to S3 Bucket

Region: us-east-1 (N. Virginia)

Enabled static website hosting

Uploaded index.html, CSS, JS, assets

Set Permissions

Disabled Block Public Access

Applied public-read bucket policy:


{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::portfolio.deepakgupta.info/*"
    }
  ]
}


Created CloudFront Distribution

Origin: S3 bucket website endpoint

Default Root Object: index.html

Enabled HTTPS (auto SSL via CloudFront)

Got CloudFront domain: d16a4uqz2l95pz.cloudfront.net



📈 Skills & Concepts Demonstrated 

AWS Cloud Fundamentals

S3 Bucket Policies & Hosting

CDN Setup with CloudFront

Performance Testing via GeoPeeker

Global delivery with minimal latency




📊 Overall Latency Reduction (%) by Region

Region	Without CDN (avg)	With CloudFront	% Reduction

Asia (SG)	~220 ms	~3 ms	~98.6%

South America (BR)	~200 ms	~4 ms	~98%

Australia	~190 ms	~3 ms	~98.4%

Europe (IR)	~100 ms	~4 ms	~96%

US (VA)	~10 ms	~2 ms	~80%

