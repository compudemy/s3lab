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

![image](https://user-images.githubusercontent.com/103466963/171045435-c6a83c71-c188-47a6-9c2e-76cb2cd09b0f.png)

![image)](https://user-images.githubusercontent.com/103466963/171044728-e2653bc6-46f3-49c7-96ac-598953f0261d.png)

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

![image](https://user-images.githubusercontent.com/103466963/171047552-975fcc73-bef7-4d86-9c1f-9ea41acb96ba.png)


This will lead us to this new screen where we can easily define policy for our bucket through this user-friendly UI.  Here we can define policies that control access to AWS products and resources.  First we will select the Policy Type that in our case is S3 Bucket Policy. We can also create different types of policies like IAM Policy, an S3 Bucket Policy, an SNS Topic Policy, a VPC Endpoint Policy, and an SQS Policy. Then we will add a statement that is a formal description of single permission. Here for Effect we will select Deny. In Principal we will write *. In Actions, we will select PutObject and in Amazon Resource Name we will enter the value we found on the previous screen with the name Bucket ARN. Note that we will add a /* after the Bucket ARN value. After that, we will click on Add Conditions.

![image](https://user-images.githubusercontent.com/103466963/171052017-6db48ecb-5014-4e61-9939-d32d4794ad4b.png)

Now here we will define that at what condition we don't want a specific object to be uploaded. We will select the Condition to Null, Key to s3:x-amz-server-side-encryption and Value to true. This means we are denying any object to be uploaded with Key s3:x-amz-server-side-encryption set to Null. Now we click on Add Condition.

![image](https://user-images.githubusercontent.com/103466963/171052477-80841a95-7b14-43b8-acfc-067605d61e10.png)

Here we can see the condition we just defined.

![image)](https://user-images.githubusercontent.com/103466963/171052635-49884da8-cc1e-400d-a182-b7c6ef3a75f7.png)

Now we will click on Add Statement. Now we will add another statement in which all the other settings will remain the same except for the condition. In Condition we will select StringNotEquals, for Key, we will select s3:amz-server-side-encryption and the Value will be set to AES256. Now again we will click on Add Condition. Here it means that for Key s3:amz-server-side-encryption if the value is not equal to AES256 then we will not allow the object to get uploaded into our bucket.

![image)](https://user-images.githubusercontent.com/103466963/171052886-54095948-20b0-4995-8832-347513b8af95.png)

Again we will click on Add Statement.


![image](https://user-images.githubusercontent.com/103466963/171053088-617e8933-4fd7-4b97-ba73-e0567a0bc121.png)


Now here we can see both our statements listed. Now we will click on Generate Policy.

![image](https://user-images.githubusercontent.com/103466963/171053786-77bb070a-c04b-4a57-8ce2-d8858a530761.png)

It returns us a JSON Document which we will use for our S3 Bucket Policy. Note that how easy it is to create policies with Policy Generator.

!image](https://user-images.githubusercontent.com/103466963/171054097-2852b019-6e2d-4f66-aa92-c71c13f9231b.png)

Now we will copy the above JSON document and paste it into our Bucket Policy and after that, we will click on Save changes.

![image](https://user-images.githubusercontent.com/103466963/171054932-8876a962-fae3-4f05-8e72-f1f9cc5e4328.png)

