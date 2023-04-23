# How to host Static Website on Amazon S3

If you want to host a static website, Amazon S3 (Simple Storage Service) is a great option. It's reliable, scalable, and easy to use. In this guide, we'll walk you through the steps to host a static website on Amazon S3.

## Introduction
Amazon S3 (Simple Storage Service) is a cloud storage service provided by Amazon Web Services (AWS). It allows you to store and retrieve data from anywhere on the internet. S3 is a highly scalable and reliable service, making it ideal for hosting websites.

A static website is a type of website that is composed of web pages with fixed content. The content of a static website is coded in HTML, CSS, and JavaScript and it does not change automatically. 

Static websites are simple to create and require no server-side processing. They are ideal for presenting information that does not need to be updated frequently, such as personal portfolios, company brochures, and event schedules. Hosting a static website is often cheaper and requires less maintenance than hosting a dynamic website, making it a popular choice for individuals and small businesses.

You can also use Amazon Route 53 (a managed Domain Name System (DNS) service) to point your domain to your Amazon S3 bucket.

## Advantages of Hosting Website on S3

There are many advantages to hosting your website on Amazon S3. Some of these include:

* **Cost-effectiveness**: You only pay for what you use, so it's a great option for websites with low traffic.

* **Scalability**: S3 can handle websites of any size and can scale up or down as needed.

* **Reliability**: S3 is a highly available service, which means that your website will be up and running at all times.
 
## Prerequisites

* An AWS account

## Set-Up Instructions

Below are the steps to deploy static Website on Amazon S3. You can follow these instructions to deploy your own static Website.

Open AWS Management console. Select S3 under Storage.

### Step 1 - Create an S3 Bucket

The first step in hosting a website on Amazon S3 is to create an S3 bucket. Here are the steps:

* Log in to your AWS account and go to the S3 dashboard.

* Click on the "Create bucket" button.

* Enter a unique name for your bucket and select the region you want to host your website in.

* Click "Create".


### Step 2 - Upload Content of your Website

The next step is to upload the content of your website to the S3 bucket you just created. Here are the steps:

* Select the bucket you just created from the S3 dashboard.

* Click on the "Upload" button.

* Select the files you want to upload and click "Upload".


### Step 3 - Add a Bucket Policy to allow Public Read Access

To make your website publicly accessible, you need to add a bucket policy to your S3 bucket. Here are the steps:

* Select the bucket you just created from the S3 dashboard.
* Click on the "Permissions" tab.
* Click on the "Bucket policy" button.
* Add the following policy: Replace [YOUR_BUCKET_NAME] with name of your bucket.

```
{
   "Version":"2012-10-17",
   "Statement":[
      {
         "Sid":"PublicRead",
         "Effect":"Allow",
         "Principal": "*",
         "Action":"s3:GetObject",
         "Resource":"arn:aws:s3:::[YOUR_BUCKET_NAME]/*"
      }
   ]
}
```

Click 'Save' button to save changes.


### Step 4 - Enable Website Hosting

The final step is to enable website hosting on your S3 bucket. Here are the steps:

Select the bucket you just created from the S3 dashboard.

* Click on the "Properties" tab.
* Click on the "Static website hosting" card.
* Select "Use this bucket to host a website".
* Enter the name of your index document (e.g. index.html) and error document (error.html).
* Click "Save".

Note the endpoint and access the site in browser:
http://{bucket-name}.s3-website-{AWS-Region}.amazonaws.com

That's it! Your static website is now hosted on Amazon S3 and publicly accessible.

