---
title: Step 5 - Run Your Task
section: Database-to-Database Replication
tutorialtype: replicate
permalink: /replicate/tutorial/db-run-task.php
---
*Optional
Before you  

After you press `Run`, Replicate will automatically switch from **Designer** mode to **Monitor** mode. 
You will be able to watch the status of the full load as it occurs, and then switch to monitoring 
change data capture as well.

![Postgres Task 5 Image](/images/postgres-task-5.png)

When **Full Load** is complete, click on the `Completed` bar to display the tables. 
There is DML activity running in the background. Click on the `Change Processing` tab to 
see it in action.

![Postgres Task 6 Image](/images/postgres-task-6.png)

If you would like to explore the data that we have delviered to Postgres, go to the folowing link:

__http://YOUR_SERVER_IP_ADDRESS:3000__

This link will open SQLPad in another window in your browser. Log in with:

* User: `admin@qlik.com`
* Password: `Aws_immersion123`

From there, click on drop down bar in the navigation pane.
You will see `mysql-src-database` as preconfigured and `postgres-tgt-database` in configuration menu

![SQLPad1 Image](/images/prod/sqlpad1.png)

Drop down to 'postgres-tgt-database` which will authenticate and bring up the database catalog

You can run any query on testdrive tables and see the new data that was loaded.

**You can run sample query** 

- Execute Query Such as `select * from testdrive."Batting";`

![SQLPad2 Image](/images/prod/sqlpad2.png)

- Also Configure a Quick Widget to see the values in postgres Tables

![SQLPad3 Image](/images/prod/sqlpad3.png)

![SQLPad4 Image](/images/prod/sqlpad4.png)

Feel free to explore the structure, etc. associated with the tables we have created. 

Now we will execute a couple of queries.

Now type into the window in SQLPad (url: ___https://YOUR_SERVER_IP_ADDRESS:3000__)

`select count(*) from testdrive."Player";`

Note the quotes around **Player** and that it begins with a capital 'P'. The schemas are 
case-sensitive, so we need the quotes in order to find the table in the query. 

Press "Run" button on top rigt of the screen to execute. This will give you 
the count of rows the Player table. That vaule should be displayed in the **Count** 
area at the bottom of the screen.

![SQLPad8 Image](/images/sqlpad8.png)

Next, we will query a few rows from the Player table to examine the data. Type 

`select * from testdrive."Player" limit 5;` 

Once again press "Run" Button on Top Right of the screen to execute it.  Five rows should be returned in the **Output** area at the bottom of the screen.
![SQLPad8 Image](/images/sqlpad9.png)

When you have seen enough, you can declare Victory! for this part of the Lab. Press `Stop`
in the top left corner of the **Replicate** console to end the task. After pressing `Stop` 
and clicking `Yes` in the confirmation dialog, click on the `TASKS` tab at the top of the screen. 
This will return you to the main window.

![Postgres Task 7 Image](/images/postgres-task-7.png)

### Summary
You just:
* Defined access and authentication into a source and a target database
* Defined the source tables you want to create and keep in sync on the target
* Configured the MySQL to Postgres task
* Captured  initial data from the source without while maintaining business continuity
  (DML activity was going on in the background to simulate users working on the source database)
* Automatically created the target tables
* Loaded the target tables
* Captured all new transactions which were happening while the initial load was running 
* Automatically began the process to apply  net new data to the target once the target was loaded
* Observed change data being recorded as it is sent to and applied at the  target 

All that in 5 easy steps!

#### You can now move on to the next part of the AWS Immersion Day [Tutorials](../tutorials).


