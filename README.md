# s3lab
# Table of Contents

# Overview on Amazon S3

# Create AWS S3 Bucket and Objects – Hands-On
# Step-1: Create an S3 Bucket

# Step-2: Create an Object

# Step-3: S3 Bucket Versioning

# Step-4: S3 Bucket Encryption

# AWS S3 Bucket Policies

# Create S3 Bucket Policies- Hands-On
# Testing AWS Bucket Policy

# Conclusion


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

Here we can see our bucket in the list of available buckets.

![image)](https://user-images.githubusercontent.com/103466963/171029469-faae612e-1f42-46c7-b792-733acb9237a7.png)

# Step-2: Upload an Object
Now we will upload objects in our S3 bucket. Note that objects are fundamental entities stored in Amazon s3. Here we will click on Upload.

![image](https://user-images.githubusercontent.com/103466963/171030457-212f1c61-f98e-4031-bc24-190c885b30b3.png)

After that, we will click on Add files. We can also add a folder. Here we can see our uploaded object named aws.png.

![image](https://user-images.githubusercontent.com/103466963/171030829-cd26f4b5-86fd-4317-8c02-356898c5fdf3.png)

We will leave the remaining settings to default and then click on Upload.

![image](https://user-images.githubusercontent.com/103466963/171031082-d9865338-b822-4e25-80ce-413a7303bdbf.png)

Here we can see the details of the object uploaded which include Properties, Permissions, and Versions. Note that we can see an Object URL over here. If we copy this URL and paste it into the browser let's see what happens.

![image](https://user-images.githubusercontent.com/103466963/171031686-1c2cbcde-d244-4b01-959e-0d7cd9435e7e.png)

The access to the file is denied and the reason is that we blocked public access while creating our S3 bucket. Now let's see what happens if we click on the Open button present in the top right corner.

![Image](https://user-images.githubusercontent.com/103466963/171032295-e829fd7f-e839-425a-a482-7f4fed03c04f.png)


![image](https://user-images.githubusercontent.com/103466963/171033955-ad35335e-7dd3-43fa-b0b3-507d3684e7bb.png)

# Step-3: S3 Bucket Versioning

Now we will explore the topic of S3 versioning. Note that with versioning we can keep multiple variants of an object in the same bucket. Versioning is used to restore, retrieve and preserve every version of every object and through it, we can also recover from both unintended user actions and application failures.


![image](https://user-images.githubusercontent.com/103466963/171034396-2d588459-9e7c-4367-9419-e531944015b2.png)

Now we will click on Edit and Enable Bucket Versioning and then click on Save Changes

![image](https://user-images.githubusercontent.com/103466963/171034770-6912feac-5a3a-4bb0-8cfd-bf6b59c1b5d3.png)

Now we will upload the aws.png file again.

![image](https://user-images.githubusercontent.com/103466963/171035205-7f8f433c-0ef1-4b48-a715-00e8b0ff9756.png)

Now when we will turn on the Show versions option, we can clearly see both the objects one which we uploaded previously without versioning enabled has Version ID equal to null and the other which we uploaded now has a Version ID.


![image)](https://user-images.githubusercontent.com/103466963/171035514-0fd3c972-72c3-4683-8103-4dbc7ea60a4d.png)

![image](https://user-images.githubusercontent.com/103466963/171035650-0ce8e90c-0b6e-45ff-8017-2109b3858eba.png)

Here for deleting an object permanently we will explicitly select an object and then click on Delete. To confirm deletion we will write permanently delete and then click on Delete objects.

![image)](https://user-images.githubusercontent.com/103466963/171036001-45a64176-8337-404e-b9ec-33ca80e05fc0.png)

Now we will explore one more thing. After uploading the aws.png object again and disabling the Show versions option we will select the object and then delete it.

![image](https://user-images.githubusercontent.com/103466963/171036250-1581754e-a1e8-494e-b1d9-4e6a0e59acd7.png)

![image](https://user-images.githubusercontent.com/103466963/171036552-386efe18-fab4-4063-821c-0bc74f77de3b.png)

Here we can see that deleting specified objects adds delete markers to them. Now we will type delete and then click on Delete objects.

![image](https://user-images.githubusercontent.com/103466963/171036750-219f56f9-691c-4c6b-8b6c-e2843771a73c.png)

Here we will enable Show versions again to view the delete marker. Note that a delete marker is a  placeholder for a versioned object named in a simple DELETE request. When we delete an object with versioning enabled the object is not deleted. The delete marker makes Amazon S3 behave as if the object has been deleted. To restore the object here, we can delete the delete marker.


![image)](https://user-images.githubusercontent.com/103466963/171041579-d2ca199d-1dd3-4ffa-9cb9-5e1ec4ba1ff3.png)

# Step-4: S3 Bucket Encryption
Now we will explore encryption in S3 Buckets. When we will get in the details of an object, we can see that Default Encryption is Disabled that is set at the bucket level.  When it is enabled the new objects that are uploaded to the S3 bucket will be encrypted by default.

![image](https://user-images.githubusercontent.com/103466963/171041901-cc57a8a2-0564-475b-afe3-6137707e0ab4.png)

When we will get into the Server-side encryption settings of the object we can specify an Encryption key. It can be either Amazon s3 key (SSE-S3) that is an encryption key created, managed, and used for us by Amazon S3, or an AWS Key Management Service key (SSE-KMS) that is protected by AWS Key Management Service. Note that to upload an object with SSE-C that is a customer-provided encryption key we need to use AWS CLI, AWS SDK, or Amazon S3 REST API.

![image](https://user-images.githubusercontent.com/103466963/171042511-a8334fb3-312b-4870-abdf-39a464aa1861.png)

![image](https://user-images.githubusercontent.com/103466963/171042691-a129275f-43c1-40ec-867f-27fbd7d9ac4a.png)

Now when we will go to the bucket level encryption it's disabled by default. We will enable it through which new objects that are stored in the bucket are automatically encrypted.  Here also either we can do encryption through SSE-S3 or SSE-KMS. If we want to use SSE-C we will have to use AWS CLI, AWS SDK, or Amazon S3 REST API as stated above.

![image](https://user-images.githubusercontent.com/103466963/171042908-9c3a8aee-fc48-4e0b-9d0c-f4bb587cb884.png)

![image](https://user-images.githubusercontent.com/103466963/171043087-6c86ea9b-341c-444f-a6e4-b78909bc1558.png)

Now when we will upload the object again in the bucket, we can see that the Default encryption is enabled.

![image](https://user-images.githubusercontent.com/103466963/171043281-10ad43e0-9763-4dd5-8e0f-c4e489df1433.png)

# AWS S3 Bucket Policies
According to what is mentioned on the official website of AWS,

A bucket policy is a resource-based AWS Identity and Access Management (IAM) policy. You add a bucket policy to a bucket to grant other AWS accounts or IAM users access permissions for the bucket and the objects in it. Object permissions apply only to the objects that the bucket owner creates.

# Create S3 Bucket Policies- Hands-On
In the Permissions section of the bucket we created earlier, we can see that there is no policy written for our bucket. We will click on Edit.

![image](https://user-images.githubusercontent.com/103466963/171044064-63bc44b7-d698-459f-a100-1b57833f7bf6.png)

This will take us to a new screen where we can see Bucket ARN which we will use when we will generate our policy through the Policy generator. Now we will click on Policy generator.

 ![image](https://user-images.githubusercontent.com/103466963/171044403-ddd4cdb1-0bdb-4959-8c49-f4ece7fa6a4d.png)






