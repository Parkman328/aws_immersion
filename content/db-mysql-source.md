---
title:   Step 1 - MySQL Source Configuration
section: Database-to-Database Replication
tutorialtype: replicate
---

**If you have done this in previous lab please skip**

The first thing we need to do is create a source endpoint. We do this by clicking the `Manage Endpoint Connections` button at the top of the screen.

![Manage Endpoints Image](/images/manage-endpoints.png)

And you will see this window.

![Add New Endpoint Image](/images/add-new-endpoint.png)

From there, click on `Add New Endpoint Connection` link or the `+ New Endpoint Connection` button 
at the top of the screen.


Once you do that you will see this window:

![New Endpoint Image](/images/new-endpoint.png)

We will now create a MySQL source endpoint:

* Replace the text **New Endpoint Connection 1** with something more descriptive 
like  `MySQL Source`, 
* make sure the `Source` radio button is selected, 
* and then select `MySQL` from the dropdown selection box.

![MySQL Source 1 Image](/images/mysql-src-1.png)

You will notice as we proceed that the content of the configuration window is context-sensitive.

![MySQL Source 3 Image](/images/mysql-src-3.png)

Fill in the blanks as indicated in the images above:

*Please note only for mysql user will be 'root'*

* Server: `127.0.0.1`
* Port: `3306`
* User: `root`
* Password: `Aws_immersion123`
* Security/SSL Mode: `None`

Click on `Test Connection` button.

Your screen should look like the followin;, indicating thatyour connection succeeded.

![MySQL Source 4 Image](/images/mysql-src-4.png)


Assuming so, click `Save` and the configuration of your MySQL source endpoint is complete.
Click `Close` to close the window.


> For more details about using MySQL as a source, please review the section  
> "Using a MyQL-Based Database as a Source" in Chapter 8 "Adding and Managing Source Endpoints" of the  
> [Qlik Replicate User Guide](/files/Qlik_Replicate_User_Guide.pdf)

#### [NEXT](../db-postgres-target) 
