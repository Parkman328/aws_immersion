---
title: Step 2 - Amazon Redshift IAM and S3 Configuration 
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

Please get the name of the bucket and what region the bucket belongs in and 

Go back to Replicate and Fill in 

* Bucket Name: `YOURBUCKETNAME`
* Region: `YOUR-REGION`



* Password: `Aws_immersion123`
* Database: `qlikdb`


![Manage Endpoints Image](/images/manage-endpoints.png)

and then press the `+ New Endpoint Connection` button.


![Manage Endpoints Image](/images/add-new-endpoint-2.png)

and you will see a window that resembles this:

![New Endpoint Image](/images/new-endpoint.png)

We will now create a Amazon Redshift Target endpoint:
* Replace the text **New Endpoint Connection 1** with something more descriptive
like  `Redshift Target`,
* make sure the `Target` radio button is selected,
* and then select `Amazon Redshift` from the dropdown selection box.

At this Point we need grab  the end point for our Redshift Instance.

Go to your EC2 Console and Find Amazon Redshift under "Services"

On your Dashboard you should see your Cluster already running

Click on your Cluster

Caputer the Endpoint name of your custer

__it should look something like this:__

Fill in the blanks as indicated in the image above:
* Host: `localhost`
* Port: `5432`
* User: `qlik123`
* Password: `Aws_immersion123`
* Database: `qlikdb`

![Redshift Target 1 Image](/images/Redshift-trg-1.png)

![Redshift Target 2 Image](/images/Redshift-trg-2.png)

and then click on `Test Connection`. Your screen should look like the following

![Redshift Target 3 Image](/images/Redshift-trg-3.png)

Due to Design of Redshift Cluster you need you are not finished. 

You must configure an IAM role with S3 Bucket precreated for you.


For more details about using RedshiftQL as a target, please review the section 
"Using a RedshiftQL-Based as a Target" in Chapter 9 "Adding and Managing Target Endpoints" of the
[Qlik Replicate User Guide](/files/Qlik_Replicate_User_Guide.pdf)

 # [NEXT](../db-config-task)