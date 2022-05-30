# s3lab
Table of Contents

Overview on Amazon S3

Create AWS S3 Bucket and Objects – Hands-On
Step-1: Create an S3 Bucket

Step-2: Create an Object

Step-3: S3 Bucket Versioning

Step-4: S3 Bucket Encryption

AWS S3 Bucket Policies

Create S3 Bucket Policies- Hands-On
Testing AWS Bucket Policy

Conclusion


In this tutorial, we will learn about AWS S3 Buckets and create one. We will also explore S3 versioning and S3 encryption and in the last, we will generate an AWS S3 Bucket policy and apply it to our S3 Bucket. But before getting started let's see what is Amazon s3
Create AWS S3 Bucket and Objects - Hands-On
Step-1: Create an S3 Bucket
First, we will log in to our AWS console then under the Services tab type S3.  Currently, we don't have any S3 Buckets available. In order to create an S3 bucket, we will click on Create bucket


![image](https://www.golinuxcloud.com/wp-content/uploads/1-21.png)

Here we will enter a bucket name that should be globally unique. Now we will enter a new name for our bucket that is globa After that, we will choose a Region where our bucket will reside. I have chosen it to be US East (Ohio). You can choose a region that is near to you. Note that the S3 console is Global.

![image](https://user-images.githubusercontent.com/103466963/171026863-c2400719-9b91-4add-bd8c-3791b7a7ac96.png)

Here we will Block all public access to our S3 bucket that are the default settings. This will be unchecked if we require public access to our buckets like in the case of hosting a website 

![image)](https://user-images.githubusercontent.com/103466963/171028250-8f65f300-990b-414a-96e9-c5b685e2c125.png)

Currently, we will keep the Bucket Versioning disabled. We will play with it in the later sections of this tutorial. We can also add tags to our bucket. We will leave the Server-side encryption disabled for now and will see it in the later sections. Now we will click on Create bucket.

![image](https://user-images.githubusercontent.com/103466963/171028929-83b4af18-e48c-407b-aa68-6d15a45deacd.png)





