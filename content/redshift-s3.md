---
title: Step 2.1 - Amazon Redshift IAM and S3 Configuration 
section: Database-to-Database Replication
tutorialtype: replicate
permalink: /replicate/tutorial/Amazon-Redshift-target.php
---

Next we need to configure our IAM Policy and Download Access and Secret Keys for Qlik Replicate to stage the data to Amazon S3 prior to writing it Redshift.

AWS IAM Policies, Users, and Roles are way AWS Secures resources and gives the right amount of access.

For this process we will give our current user access to all S3 buckets but your Cloud admin can secure it so user/role only has access to a single bucket we need.

First grab the bucket name

![S3 Bucket](/images/redshift-s3-1.png)

Go to AWS S3 and you should see a bucket name that and in "-qlikreplicate"

![S3 Bucket Name](/images/redshift-s3-2.png)

Click on the bucket and "Properties"

![S3 Bucket Properties](/images/redshift-s3-3.png)

Please get the name of the bucket and what AWS Region the bucket belongs in

![S3 Bucket Properties](/images/redshift-s3-4.png)

Go back to Qlik Replicate and Fill in following from End Point Configurations

* Bucket Name: `YOURBUCKETNAME`
* Region: `YOUR-REGION`

Now you will need to add an user with full s3 access. 
Go into IAM section of AWS add an User
Add a Role for that with S3Full Access.

__for this tutorial we will just logged in user with full s3 acces__

Go to IAM section on your AWS Console by clicking on services(top left) -> IAM.  If it does not show up you can search for 'IAM' as well.

![S3 Bucket Properties](/images/redshift-s3-5.png)

At this point you will see IAM dashboard; click on `Users`

![S3 Bucket Properties](/images/redshift-s3-6.png)

Click on and press `Add User`

![S3 Bucket Properties](/images/redshift-s3-11.png)

Input your Amazon S3 User Name:

* __User Name: qlik-replicate__
* __Select Programmatic access only__

![S3 Bucket Properties](/images/redshift-s3-12.png)

Press Button `Next Permissions`

![S3 Bucket Properties](/images/redshift-s3-13.png)

Press Button `Next Permissions`

![S3 Bucket Properties](/images/redshift-s3-14.png)

Optional Add Tags a nd Press Button `Next Review`

![S3 Bucket Properties](/images/redshift-s3-16.png)

Review you User name and Press Button `Create User`

![S3 Bucket Properties](/images/redshift-s3-15.png)

**At this point your new user with Full Amazon S3 privilages are created**

Copy Access Key and Secret Key to Qlik Replicate Connection windown 
(Click on Show on access key to view the key)

![S3 Bucket Properties](/images/redshift-s3-17.png)

Donwload your keys or copy the keys into Qlik Replicate Connection Window.(Please Click on Show to see your secret key)

Please copy the keys to your Qlik Replicate Connection Window

* Access Key: `YOUR ACCESS KEY`
* Your Secret Key: `YOUR SECRET KEY`

![S3 Bucket Properties](/images/redshift-s3-4.png)

Press `Test` to test connection

![S3 Bucket Properties](/images/redshift-s3-19.png)

>Note if you run into issues with Qlik Replicate complaining about S3 access please verify the qlik-replicate user has access to S3 buckets.

![S3 Bucket Properties](/images/redshift-s3-18.png)





For more details about using RedshiftQL as a target, please review the section 
"Using a RedshiftQL-Based as a Target" in Chapter 9 "Adding and Managing Target Endpoints" of the
[Qlik Replicate User Guide](/files/Qlik_Replicate_User_Guide.pdf)

 # [NEXT](../redshift-config-task)