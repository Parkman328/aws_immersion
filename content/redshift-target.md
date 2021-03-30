---
title: Step 2 - Amazon Redshift Target Configuration 
section: Database-to-Database Replication
tutorialtype: replicate
permalink: /replicate/tutorial/Amazon-Redshift-target.php
---

Next we need to configure our Redshift target endpoint. The process is much the same as you saw 
with the MySQL source but for Redshift we need to have S3 Bucket, and once again you will note that the configuration process is
context-sensitive as we move along.

As before, the first step in the configuration process is to tell Replicate that we want to 
create a new endpoint. If you are back on the main window, you will need to click on 
`Manage Endpoint Connections` button.

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

![New Endpoint Image](/images/redshift-trg-1.png)

At this Point we need grab  the end point for our Amazon Redshift Instance.

Go to your EC2 Console and Find Amazon Redshift under "Services"

![New Endpoint Image](/images/redshift-trg-3.png)

On your Dashboard you should see your Cluster already running.

![New Endpoint Image](/images/redshift-task-2.png)

Navigate to the Cluster and you should see the properties of your cluster looking something like.

Click on the button to copy the endpoint.

![New Endpoint Image](/images/redshift-trg-4.png)

__Once the endpoint is copied you should see that it has port number and database appended.__

__Manually remove the values and use endpoint as a reference to fill in the variables.__


![New Endpoint Image](/images/redshift-trg-2.png)

Fill in the blanks as indicated in the image above:
* Host: `YOUR REDSHIFT ENDPOINT`
* Port: `5432`
* User: `qlik123`
* Password: `Aws_immersion123`
* Database: `qlikdb`

Due to Design of Redshift Cluster you need  to use S3 as intermediate staging area

Next steps will walk you through that steps.

> For more details about using RedshiftQL as a target, please review the section    
> "Using a RedshiftQL-Based as a Target" in Chapter 9 "Adding and Managing Target Endpoints" of the   
> [Qlik Replicate User Guide](/files/Qlik_Replicate_User_Guide.pdf)

 # [NEXT](../redshift-s3)