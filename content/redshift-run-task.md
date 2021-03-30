---
title: Step 5 - Run Your Task
section: Database-to-Database Replication
tutorialtype: replicate
permalink: /replicate/tutorial/db-run-task.php
---

After you press `Run`, Replicate will automatically switch from **Designer** mode to **Monitor** mode. 
You will be able to watch the status of the full load as it occurs, and then switch to monitoring 
change data capture as well.

![Redshift Task 5 Image](/images/redshift-task-8.png)

When **Full Load** is complete, click on the `Completed` bar to display the tables. 
There is DML activity running in the background. Click on the `Change Processing` tab to 
see it in action.

![Redshift Task 6 Image](/images/redshift-task-7.png)

If you would like to explore the data that we have delviered to Redshift please go to SQLPad

* url: ___https://YOUR_SERVER_IP_ADDRESS:9000__

Connect to your Cluster by Creating your Connection

Press the Edit on Top Right at SQLPad

![SQL Pad Edit](/images/sqlpad5.png)

Press the Edit on Top Connections

![SQL Pad Edit](/images/sqlpad6.png)

* Connection name: `Redshift`
* Driver: `Redshift`
* Host: **REDSHIFT_CLUSTER_NAME**
* Port: `5439`
* Database: `testdrive`
* Database Username: `qlik123`
* Database Password: `Aws_immersion123`

![SQL Pad Edit](/images/sqlpad7.png)

Now type 

`select count(*) from testdrive."Player";`

Note the quotes around **Player** and that it begins with a capital 'P'. The schemas are 
case-sensitive, so we need the quotes in order to find the table in the query. Highlight that 
line and press the 'Run' button at the top of the screen to execute. This will give you 
the count of rows the Player table. That vaule should be displayed in the **Data Output** 
area at the bottom of the screen.

![Redshift Task 4 Image](/images/redshift-task-4.png)

Next, we will query a few rows from the Player table to examine the transformation. 

Type `select fullname from testdrive."Player" limit 5;` 

Press `Run` Button.  Five rows should be returned in the **Data Output** area 
at the bottom of the screen.



You will see the **fullName** column that we created during the transformation. You will also note that the values set in that column are just
as we coded them to look in the transformation.

![Redshift Task 3 Image](/images/redshift-task-3.png)


When you have seen enough, you can declare Victory! for this part of the Lab. Press `Stop`
in the top left corner of the **Replicate** console to end the task. After pressing `Stop` 
and clicking `Yes` in the confirmation dialog, click on the `TASKS` tab at the top of the screen. 
This will return you to the main window.

### Summary
You just:
* Defined access and authentication into a source and a target database
* Defined the source tables you want to create and keep in sync on the target
* Configured the MySQL to Redshift task
* Configured a transformation that added a new column to the Player table
* Captured  initial data from the source without while maintaining business continuity
  (DML activity was going on in the background to simulate users working on the source database)
* Automatically created the target tables
* Loaded the target tables
* Captured all new transactions which were happening while the initial load was running 
* Automatically began the process to apply  net new data to the target once the target was loaded
* Observed change data being recorded as it is sent to and applied at the  target 

All that in 5 easy steps!

You are now finished with AWS Immersion Day  Tutorials.


