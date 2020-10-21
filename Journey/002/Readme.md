# Create S3 static website

## Introduction

The purpose of this exercise is to create a simple S3 static site with a few lines of HTML.

## Prerequisite

No prerequistes but having some familiarity with the S3 web console can help.

## Use Case

- The use case for this project would be to host a cheap simple static website on S3.

## Cloud Research

- The creation of the S3 bucket thru the console is pretty straight forward.  One thing I encountered at the bucket creation was it prompts you to block public access to the bucket.  Public access is required to hit the website from the internet.  So leave these options not enabled.  Also keep in mind that you also need to craft a bucket policy to allow users to access the site.  
- 🖼️ Show as many screenshot as possible so others can experience in your cloud research.

## Try yourself

✍️ Add a mini tutorial to encourage the reader to get started learning something new about the cloud.

### Step 1 — Create S3 Bucket

1. log into AWS console \ go to S3
2. Click Create Bucket
3. On the Name and Region page - Name bucket (must be unique and not already in use globally) \ Select region, click next.
4. On the Configure Options page - leave defaults on this page, click next.
5. On the Permissions page, uncheck Block all public access, click next. 
6. Click Create Bucket. 



### Step 2 — Enable Static Website on bucket

1. Click on the bucket you just created on the main S3 page.
2. Click on Properties tab, click on Static website hosting
3. Click Use this bucket to host a website radio button
4. in the Index document field, type index.html (or whatever you want to call your default page)
5. Click Save.



### Step 3 — Create Index.HTML file

1. Open your prefered IDE or text editor
2. Craft an HTML file which displays some text etc.  Below is a sample taken from the AWS documentation.  You are encouraged to write your own or at the very least type the example out. Don't copy and paste.  We are here to learn!

index.html Example:

<html xmlns="http://www.w3.org/1999/xhtml" >
<head>
    <title>My Website Home Page</title>
</head>
<body>
  <h1>Welcome to my website</h1>
  <p>Now hosted on Amazon S3!</p>
</body>
</html>

3. Save the file.  It must be the same name the index file name you provided in index document field (step 2).
4. Upload the file to your bucket using the S3 console.
    a. Select bucket
    b. In the Overview tab \ click Upload.
    c. browse for the file and click Upload.



### Step 4 — Create Bucket Policy

1. Under the Permissions tab click Bucket Policy.
2. Define the bucket policy to allow read access to everyone.  This allows anyone to access it from the internet.  Below is a policy taken from AWS documentation to allow for this.  As always type it out don't copy and paste.  !!!Do not use this bucket policy if you have sensitive data in the bucket it will be accessible by anyone!!!

{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": [
                "s3:GetObject"
            ],
            "Resource": [
                "arn:aws:s3:::YOURBUCKETNAMEHERE/*"
            ]
        }
    ]
}

3. Click Save

### Step 5 — Test Static Site

1. Open a new tab in your broswer and browse to the S3 URL and see if your page loads. 
    a. You can get the S3 URL in the Static website hosting section of the properties of the S3 bucket on the console.

## ☁️ Cloud Outcome

The project was a success, after performing all the steps the simple S3 static bucket returned the webpage properly.  

## Next Steps

This project is a stepping stone to attempt to setup a fully functional static blog site on S3.  This project will be continued in future projects of #100daysofcloud

## Social Proof

[Tweet](https://twitter.com/realmawsb/status/1318807728396079104)

##LEGAL DISCLAIMER 

The material embodied in this Repository and all resources provided within is provided to you "as-is" and without warranty of any kind, express, implied or otherwise, including without limitation, any warranty of fitness for a particular purpose. In no event shall the Author be liable to you or anyone else for any direct, special, incidental, indirect or consequential damages of any kind, or any damages whatsoever, including without limitation, loss of profit, loss of use, savings or revenue, or the claims of third parties, whether or not the Author has been advised of the possibility of such loss, however caused and on any theory of liability, arising out of or in connection with the possession, use or performance of this Repository and all resources provided within.