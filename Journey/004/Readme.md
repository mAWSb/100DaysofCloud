<!-- This template removes the micro tutorial for a quicker post and removes images for a full template check out the 000-DAY-ARTICLE-LONG-TEMPLATE.MD-->

# Created static version of wordpress site in AWS S3 \ setup Route 53 DNS for the site

## Introduction

This project ended up being a multi step project that effectively creates a static version of a WordPress site and then is hosted in an S3 bucket.  This is accomplished by using The wordpress plug-in simply static, then creating \ adding the static files to a AWS S3 bucket, then setting up Route 53 DNS to point the S3 endpoint.  Additionally a second S3 bucket is created to configure HTTP redirection of requests to www.yourdomain.com to the root domain yourdomain.com (where the site is). 

## Use Case

- A use case for this procedure would be if you need a fast loading site or want to try to reduce the attack surface of your wp site.  There are pro's and con's to this setup and I would not recommend this as a catch all for wordpress deployments.

## Cloud Research

- In working through getting this setup, I found that simply static creates a javascript file and puts it into a wp-includes folder.  If you try to upload the js file inside the folder to the S3 bucket all the formatting etc will not load.  You need to take this file out of the folder and upload it directly. Once I did that the page loaded correctly.  Another configuration that I found interesting or at least was new to me was creating the second bucket for redirects.  For a standard server wordpress install I have running in EC2, I only added a DNS record for the www. subdomain.  It appears using the static site a second bucket must be created and configured for redirction to the root domain for this to work.

- Overall this was an fun project and I gleaned a lot from it.  One thing that I want to investigate more is that the links on the page to othe pages on the site point to localhost.  This makes sense to me as the site I made static was local.  What I need to do is determine how I can point to these pages.  To be continued on that, but the main goal of hosting a wp static site in S3 bucket with route 53 was a success.


## Social Proof


[Tweet](https://twitter.com/realmawsb/status/1319574238316068864)
