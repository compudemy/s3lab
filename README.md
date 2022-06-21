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

# Testing AWS Bucket Policy
Now we will upload aws.png again into our S3 bucket but this time without specifying any encryption key. Let's see what happens.

![image](https://user-images.githubusercontent.com/103466963/171055243-5e7828ec-8ce9-448a-b867-b7190dc75a5d.png)

We will receive an error message Upload Failed and we can clearly see that the access is denied since our object was not encrypted with AES256 i.e SSE-S3 while we uploaded it.

![image](https://user-images.githubusercontent.com/103466963/171055384-cd67ccff-943f-4a9a-b902-57631f2c279f.png)

Now we will upload the object again but this time we will specify an encryption key by overriding default encryption bucket settings and then select SSE-S3 and click on Upload.


![image](https://user-images.githubusercontent.com/103466963/171055649-244f510b-4f7d-41c6-942f-d1f5d379fa44.png)

Here we can see that object has been uploaded successfully as it satisfies conditions set in our bucket policy.

![image](https://user-images.githubusercontent.com/103466963/171055761-838f4b47-5a49-4ccf-b3ed-b59497325c86.png)

# Conclusion
With this, we have come to the end of our tutorial. In this tutorial, we learned about

S3 Buckets and Objects

S3 Versioning

S3  Encryption

S3 Bucket Policy

LAB 2

Lab Details

This lab walks you through Amazon Simple Storage Service. Amazon S3 has a simple web interface that you can use to store and retrieve any amount of data(at any time) from anywhere on the web. In this lab we will demonstrate AWS S3 by creating a sample S3 bucket, uploading an object to the S3 bucket and setting up the bucket permission and policy.

Tasks
Log into the AWS Management Console.

Create an S3 bucket.

Upload an object to S3 Bucket.

Access the object on the browser.

Change S3 object permissions.

Setup the bucket policy and permission and test the object accessibility.

![image](https://user-images.githubusercontent.com/103466963/174650577-99b85d0a-aa3e-44ed-8840-49ab350267e7.png)

Set up the bucket name. S3 bucket name are globally unique, choose a name which is available.
Click on Next

![image](https://user-images.githubusercontent.com/103466963/174651003-7300ab5f-e2dd-4d0d-876f-7e1b4905eda6.png)

Leave other settings as default and click on Next

![image](https://user-images.githubusercontent.com/103466963/174651306-2af5336d-aeb5-4ea4-8f53-44232dbffafd.png)

Leave other settings as default and click on Next

![image](https://user-images.githubusercontent.com/103466963/174651549-1246446a-8b00-4830-8c66-bddfedff3388.png)

Leave other settings as default and click on Create bucket

![image](https://user-images.githubusercontent.com/103466963/174651713-b0498929-f077-496c-a6c6-15d19ac317ab.png)

Click on your bucket name.

![image](https://user-images.githubusercontent.com/103466963/174651883-39fbdbb7-a63c-49ea-a306-498c847c1bd3.png)

Click on Upload

![image](https://user-images.githubusercontent.com/103466963/174652030-a1ef5274-0ed9-42fe-a4b1-b496a3474149.png)

Click on Add files, and choose a file from your computer.

![image](https://user-images.githubusercontent.com/103466963/174687559-479a5251-7a78-408a-b037-990b2c933dad.png)

After choosing your file, click on Next

![image](https://user-images.githubusercontent.com/103466963/174687640-91884ef2-64e4-4209-b751-ea5c9099b322.png)

Click on Next

![image](https://user-images.githubusercontent.com/103466963/174687683-819922d3-8569-4dec-a464-129b8835f3d0.png)

Click on Next

![image](https://user-images.githubusercontent.com/103466963/174687766-c535b06d-a8ee-42d0-95d8-4b4dd2ef7b63.png)

Click on Upload.

![image](https://user-images.githubusercontent.com/103466963/174688105-adaed77a-4405-44ef-8928-19314a3e7044.png)

You could see the uploading procession below.

![image](https://user-images.githubusercontent.com/103466963/174688522-1a149c03-92e3-458a-b39d-5cc007223fc8.png)

Now you have a private S3 bucket with a private object uploaded, which means you cannot visit it through Internet.

Change Bucket Permission

Change the permission of the bucket to make the image available publicly.

Click on your object in the bucket, You will see the object details like owner, size, link, etc.

![image](https://user-images.githubusercontent.com/103466963/174688649-4ff46a68-685b-46d8-a127-07a28bc3ef79.png)

A URL will be listed under Object URL

https://mys3bucketwhizlabs.s3.amazonaws.com/smiley.jpg

Open image Link in a new tab.
You will see an AccessDenied message, which means the object is not publicly accessible.

![image](https://user-images.githubusercontent.com/103466963/174689068-a1b4f9ad-7075-4654-acc9-b648320f946b.png)

Go back to your bucket and click on Permissions

![image](https://user-images.githubusercontent.com/103466963/174689154-9591fc9a-4c9a-4c96-b7cb-2c524a036806.png)

Click on Everyone under the Public access, and click on Read object on the right of pop-up window. Then click on Save

![image](https://user-images.githubusercontent.com/103466963/174689240-498c446d-59bf-4911-8fd6-6b170290c2d3.png)

Now its state switches to Read Object - Yes

![image](https://user-images.githubusercontent.com/103466963/174689296-cb0f49ee-d47e-4232-96b1-aad3e11ac1a8.png)

Click on Overview, and click on your Object URL again

![image](https://user-images.githubusercontent.com/103466963/174689388-b3f98037-eaff-4187-a899-6cab52e4d254.png)

Create a Bucket Policy

In the previous step, you granted read access only to a specific object. 

If you wish to make all objects inside a bucket available publicly, you can achieve this by creating a bucket policy.

Go to the bucket list and click on your bucket name

![image](https://user-images.githubusercontent.com/103466963/174689535-0328020a-4926-4899-ad4e-a1cfcaa35f9d.png)

Click the Permissions tab, then configure the following

![image](https://user-images.githubusercontent.com/103466963/174689623-2719f342-a9ca-4089-b948-474aa20a4abc.png)

Click on Bucket Policy

![image](https://user-images.githubusercontent.com/103466963/174689695-a628a5b7-ee5f-473f-8ccb-9674c15623f9.png)

A blank Bucket policy editor is displayed.

Copy the ARN of your bucket to the clipboard.e.g, arn:aws:s3:::s3bucket180

Replace your bucket ARN with the ARN listed in the JSON below, then copy the entire policy.

<img width="821" alt="Screen Shot 2022-06-20 at 19 51 15" src="https://user-images.githubusercontent.com/103466963/174690234-451dd845-cced-4a28-bfe8-ff538afd89cf.png">

Click on Save

![image](https://user-images.githubusercontent.com/103466963/174690435-93b1d783-ff68-46f8-83e2-bcd958eef65b.png)

Test Public Access

Go back to your bucket list, then click on your bucket.

Upload another file.

Leave all of the settings as default

![image](https://user-images.githubusercontent.com/103466963/174690566-aa3a938a-dc99-413b-842e-193f067d4ec9.png)

Click on your new object, and click on the Object URL

![image](https://user-images.githubusercontent.com/103466963/174690637-e55d5368-ac18-42e3-b95a-0e9334d762ee.png)
Success

Completion and Conclusion

You have successfully created a new AWS S3 Bucket.

You have successfully uploaded an image to the S3 bucket.

You have learned to change S3 object permissions.

You have learned how to create an S3 bucket policy.

How to enable versioning Amazon S3

https://play.whizlabs.com/site/task_details?lab_type=1&task_id=21&quest_id=35

Lab Details

This lab walks you through the steps on how to enables versioning on an AWS S3 Bucket. 

Versioning allows you to keep multiple versions of an object in one bucket.

Task Details

Log into the AWS Management Console.

Create an S3 bucket.

Enable object versioning on the bucket.

Upload a text file to the S3 Bucket.

Test object versioning by changing the text file and re-uploading it.

Architecture Diagram

<img width="749" alt="Screen Shot 2022-06-20 at 20 09 02" src="https://user-images.githubusercontent.com/103466963/174691319-7e84ae02-5d6e-42d3-8881-e9bd89a92cc2.png">

S3 Configuration

Service -> S3

Create an S3 Bucket

On the S3 dashboard, click on Create bucket and fill in the bucket details.

![image](https://user-images.githubusercontent.com/103466963/174691667-e0a753f1-ecab-45b1-8a21-b59192694cb7.png)

Bucket name: Enter yourBucketName

Note: S3 bucket names are globally unique, choose a name which is available.

Region: Select US East (N. Virginia)

Leave other settings as default.

Click on Create

![image](https://user-images.githubusercontent.com/103466963/174691930-6aedc778-e60d-470d-b460-6e43d8ac84bb.png)

Close the pop up window if it’s still open.

![image](https://user-images.githubusercontent.com/103466963/174692073-788a8564-ab55-43b9-89c9-96e1e24457cb.png)

Enable Versioning on the S3 bucket

Go to the bucket list and click on your bucket name whizlabs234

![image](https://user-images.githubusercontent.com/103466963/174692282-a4048bf7-e820-49e3-bb6c-871f75583b5a.png)

Click on Properties.

![image](https://user-images.githubusercontent.com/103466963/174692383-1a1ff08f-a09b-4d7d-9d35-3d9185dcf805.png)

Choose Versioning.

![image](https://user-images.githubusercontent.com/103466963/174692570-71d6ff61-c4be-4241-af08-b013ee24e28d.png)

Choose Enable versioning and click on Save.

![image](https://user-images.githubusercontent.com/103466963/174692690-b3bd0850-b0ec-4df1-97e3-b40561699665.png)

Now versioning on the S3 bucket is enabled.

![image](https://user-images.githubusercontent.com/103466963/174693296-a275148e-ba76-4d78-ae6a-c08f040c7c31.png)

Upload an object

Upload any file from your local machine.

On the S3 Buck list page, Click on youBucketName

Click on Overview tab.

Click on the Upload button.

![image](https://user-images.githubusercontent.com/103466963/174693478-b8610281-14fa-405d-b5f9-5c719853295b.png)

![image](https://user-images.githubusercontent.com/103466963/174693512-263cd659-ca27-4705-af1c-44bc808b0cc7.png)

Click on the Add files button.

![image](https://user-images.githubusercontent.com/103466963/174693578-5e1a6ddd-9efc-4e06-accb-7b74defd9fa9.png)

Browse for the file you want to upload.

![image](https://user-images.githubusercontent.com/103466963/174693654-0eda149c-160c-43fc-b280-fdc3d9633035.png)

Click on Next and Grant public read access to this project(s)

Click on the Upload button.

![image](https://user-images.githubusercontent.com/103466963/174693732-05b422df-ab0e-47a1-a244-d292cf8616c0.png)

You can watch the progress of the upload from within the transfer panel at the bottom of the screen. 

If it’s a small file, you might not see the transfer. 

Once your file has been uploaded, it will be displayed in the bucket.

![image](https://user-images.githubusercontent.com/103466963/174693823-244a878d-1dba-486e-8da2-6000345fdcb3.png)

Make the bucket public with a Bucket Policy

Go to the bucket list and click on your bucket name.

![image](https://user-images.githubusercontent.com/103466963/174693921-fbcdbdd8-28f3-451e-af8b-c1d33b3c0339.png)

Click the Permissions tab to configure your bucket:

In the Permissions tab, click on Bucket Polity

A blank Bucket policy editor is displayed.

Before creating the policy, you will need to copy the ARN (Amazon Resource Name) of your bucket.

Copy the ARN of your bucket to the clipboard. It is displayed at the top of the policy editor. its look like ARN: arn:aws:s3:::your-bucket-name

![image](https://user-images.githubusercontent.com/103466963/174694110-47113b9c-aee0-407d-a1ed-9a2683c9d221.png)

![image](https://user-images.githubusercontent.com/103466963/174694136-834dddeb-7751-4d75-97d1-5edac17188a6.png)

In the policy below, update your bucket ARN in the Resource key value and copy the policy code.

Paste the bucket policy into the Bucket policy editor.

<img width="806" alt="Screen Shot 2022-06-20 at 20 51 06" src="https://user-images.githubusercontent.com/103466963/174694308-c21d1fcb-ef1e-45a7-92de-7135ed9b4ef3.png">

![image](https://user-images.githubusercontent.com/103466963/174694339-e3d27842-f3ff-4ff6-9202-8f4fd7590974.png)

Click on Save

![image](https://user-images.githubusercontent.com/103466963/174694389-7749a752-0827-416f-8f61-70b2594f016d.png)

Click on Overview

![image](https://user-images.githubusercontent.com/103466963/174694551-10434879-2bb5-43e7-9035-ac54afd7400c.png)

Now open the text file link in your browser and you should see the text in file.

![image](https://user-images.githubusercontent.com/103466963/174694626-051ae13e-02e4-46b1-9134-2447706afd55.png)

![image](https://user-images.githubusercontent.com/103466963/174694674-e117d673-3a8d-4dc4-8589-d706442e1da2.png)

Upload the same object with different content

Upload the same file with different content from your local machine.

On the S3 Buck list page, Click on youBucketName

Click on Overview tab.

Click on the Upload button.

![image](https://user-images.githubusercontent.com/103466963/174838772-c9d53f89-dcce-40ef-9679-dcabee1f6857.png)

![image](https://user-images.githubusercontent.com/103466963/174838865-36c4213d-ce15-49f1-9c41-da04f3bd6265.png)

Click on the Add files button.

![image](https://user-images.githubusercontent.com/103466963/174839008-364c6fc7-666a-43f0-aaec-2e28c06271c8.png)

Browse for the file you want to upload.

![image](https://user-images.githubusercontent.com/103466963/174839314-da9510d3-a059-458a-9f3a-a7521b66b07b.png)

Click on Next and Grant public read access to this project(s)

Click on the Upload button.

![image](https://user-images.githubusercontent.com/103466963/174839537-a0deea3b-a946-4db7-9cc3-4b61d9a74653.png)

You should see the latest version of the file you uploaded.

![image](https://user-images.githubusercontent.com/103466963/174839714-c7c63b65-6311-4e7c-ba38-99f1c1b177ec.png)

![image](https://user-images.githubusercontent.com/103466963/174840035-561dae1e-ef17-4df7-9eab-2762e1d61f2e.png)

Testing a previous version of the file

To enable the old version of the file, we need to delete the latest version of the file.

Click on object URL

![image](https://user-images.githubusercontent.com/103466963/174840231-27aab0f4-4ceb-4fc3-a78f-02feac3b5521.png)

![image](https://user-images.githubusercontent.com/103466963/174840763-3b0cb570-aa4e-4eed-9764-a6dfd814e5af.png)

Click on the file name.

On the top section (next to the object name) you can find a drop down of all file versions called 

Latest version

![image](https://user-images.githubusercontent.com/103466963/174840971-bc9f3dca-c415-41df-9b30-f5ca685ec6c5.png)

Click on the drop down and delete the latest version of your file.

![image](https://user-images.githubusercontent.com/103466963/174841053-768a480f-134d-44f6-a9c9-48890d8f2068.png)

![image](https://user-images.githubusercontent.com/103466963/174841277-42ea1be0-0508-42ce-a330-6c5d98367415.png)

Completion and Conclusion

You have successfully created an S3 Bucket.

You have successfully enabled Object Versioning on the Bucket.

You have successfully uploaded a test file into the Bucket and tested its versioning.

Creating an S3 Lifecycle Policy

https://play.whizlabs.com/site/task_details?lab_type=1&task_id=45&quest_id=35

Lab Details

This Lab walks you through the steps on how to create a Lifecycle Rule for an object in an S3 Bucket.

Lab Tasks

Log into the AWS Management Console.

Create S3 Bucket and upload and object into the bucket.

Create a Lifecycle Rule on the object.

Create Transition types.

Create Transition Expiration.

Test the Lifecycle Rule on the uploaded object.

S3 Configuration

Create an S3 Bucket

On the S3 dashboard, click on Create bucket and fill in the bucket details.

![image](https://user-images.githubusercontent.com/103466963/174851671-8f0cbaf9-abcc-40b1-bcfc-f3911ea0d90b.png)

Bucket name: Enter inputYourBucketName

Note: S3 bucket names are globally unique, choose a name which is available.

Region: Select US East (N. Virginia)

Leave other settings as default.

Click on Create

![image](https://user-images.githubusercontent.com/103466963/174852054-57a637e8-8cbf-4e47-bb03-9004472e508e.png)

Close the pop up window if it’s still open.

![image](https://user-images.githubusercontent.com/103466963/174852228-1cf0097b-1dbe-422f-bbda-e81ca6afe54a.png)

Upload an object

Upload any file from your local machine.

On the S3 Buck list page, Click on youBucketName

Click on Overview tab.

Click on the Upload button.

![image](https://user-images.githubusercontent.com/103466963/174852565-d8ef4e19-75cd-4eaa-8380-30ff26dc39eb.png)

![image](https://user-images.githubusercontent.com/103466963/174852632-b430b17c-9d7c-4b1c-86d9-7927b9f5119e.png)

Click on the Add files button.

![image](https://user-images.githubusercontent.com/103466963/174852779-59a45be4-21bc-421f-96f0-328c3f797c50.png)

Browse for the file you want to upload.

![image](https://user-images.githubusercontent.com/103466963/174852954-eca0768c-e482-4dbb-b224-2b8b7cc02ba1.png)

Click on Next and Grant public read access to this project(s)

Click on the Upload button.

![image](https://user-images.githubusercontent.com/103466963/174853151-e40897f5-10db-427c-ad2a-07ce6159e6ea.png)

You can watch the progress of the upload from within the transfer panel at the bottom of the screen. 

If it’s a small file, you might not see the transfer. 

Once your file has been uploaded, it will be displayed in the bucket.

![image](https://user-images.githubusercontent.com/103466963/174853343-b5006b3b-8d44-4bef-857d-18e38ca31307.png)

Creating a Lifecycle Rule

Click on the Management tab.

![image](https://user-images.githubusercontent.com/103466963/174853590-76ef7569-80c2-43b3-8d8c-7c5ed528a2f6.png)

Click on Add lifecycle rule to create a lifecycle rule for the uploaded object.

![image](https://user-images.githubusercontent.com/103466963/174853924-ae396b7e-6246-4bc5-ada5-9e9e569e3729.png)

Enter the rule name: tmpLifecycle

Add a filter to limit the scope to prefix/tags: tmp

Choose prefix tmp from the drop-down and click Next.

![image](https://user-images.githubusercontent.com/103466963/174854133-6f60b8bf-131b-49ce-8636-0be0ddd8e95e.png)

Storage class transition: Select Current version

![image](https://user-images.githubusercontent.com/103466963/174854309-b7ba69ee-08bd-4e90-a885-0ec069a22188.png)

For current versions of objects: Click Add transition

Note: currently versioning is disabled so we can’t access previous versions of the object.
Object Creation: Select Transition to One Zone-IA after from the drop-down list.

Days after creation: Enter 35.
Click on Add transition.

Select Transition to Glacier after from the drop-down list. When asked for a number of days before moving to Glacier, enter 90.

Click on the checkbox saying I acknowledge that this lifecycle rule will increase the one-time lifecycle request cost if it transitions to small objects.

Click on Next.

Note:

Initially, when the object is uploaded, it will be in the standard storage class.

When we create a LifeCycle Policy, the object uploaded using the Lifecycle rule will be migrated to One Zone-IA after 35 days. This means the object will be available only in a Single Availability Zone after 35 days.

After 90 days, our object will be migrated to Glacier. This means our object will be in an archived state. You would have to retrieve the object from Glacier before accessing it.

![image](https://user-images.githubusercontent.com/103466963/174855156-d96a76c7-5dba-4273-9a02-6d241a30a067.png)

Create Expiration: Select Current version

Expire the current version of an object: Enter 120.

Select the Clean up incomplete multipart uploads check-box.

Note: Leave the number of days at 7 (Default value). This means that objects which are not properly uploaded will be deleted after 7 days.

![image](https://user-images.githubusercontent.com/103466963/174855296-3da4d3e5-d227-4bc9-b7e7-c4180e613115.png)

Before saving, verify the configurations (you can go back and edit later if you need to change anything). Click Edit.

Click on Save.

![image](https://user-images.githubusercontent.com/103466963/174855662-3a5d4d17-2afb-47cd-a22c-d09f69eb3fea.png)

The Lifecycle Rule for our object will now be created and enabled.

![image](https://user-images.githubusercontent.com/103466963/174855767-ca9d52c1-ac32-42cd-b22c-d9ed28105741.png)

Completion and Conclusion

You have successfully used the AWS management console to create a Lifecycle Rule for the object in the S3 bucket.

You have configured the details of a Lifecycle Rule.













