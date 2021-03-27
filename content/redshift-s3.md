---
title: Step 2.1 - Amazon Redshift IAM and S3 Configuration 
section: Database-to-Database Replication
tutorialtype: replicate
permalink: /replicate/tutorial/Amazon-Redshift-target.php
---

Next we need to configure our IAM Policy and Download Access and Secret Keys for Qlik Replicate to stage the data to Amazon S3 prior to writing it Redshift

AWS IAM Policies, Users, and Roles are way AWS Secures resources and gives the right amount of access.

For this process we will give our current user access to all S3 buckets but your Cloud admin can secure it so user/role only has access to a single bucket we need.

First grab the bucket name

Go to AWS S3 and you should see a bucket name that and in "-qlikreplicate"

Click on the bucket and "Properties"

Please get the name of the bucket and what region the bucket belongs in

Go back to Qlik Replicate and Fill in following from End Point Configurations

* Bucket Name: `YOURBUCKETNAME`
* Region: `YOUR-REGION`

Now you will need to add an user with full s3 access. 
Go into IAM section of AWS add an User
Add a Role for that with S3Full Access.

* Access Key: `YOUR ACCESS KEY`
* Your Secret Key: `YOUR SECRET KEY`

Press `Test` to test connection
.



For more details about using RedshiftQL as a target, please review the section 
"Using a RedshiftQL-Based as a Target" in Chapter 9 "Adding and Managing Target Endpoints" of the
[Qlik Replicate User Guide](/files/Qlik_Replicate_User_Guide.pdf)

 # [NEXT](../redshift-config-task)