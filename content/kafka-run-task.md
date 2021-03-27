---
title: Step 4 - Run Your Task
section: Streaming Data to Kafka
tutorialtype: replicate
permalink: /replicate/tutorial/kafka-run-task.php
---

When you press `Run`, Replicate will automatically switch from **Designer** mode to **Monitor** mode. 
You will be able to watch the status of the full load as it occurs, and then switch to monitoring 

![Kafka Task 9 Image](/images/kafka-task-9.png)

While Monitoring login to Kafdrop and take a look. __url:YOUR_SERVER_IP_ADDRESS:9000__

Initially you will not see your Kafka Topics configured for each table but after a few second you see it populate from Mysql via Qlik Replicate.

Pre-Load:

![Kafdrop 1](/images/prod/kafdrop.png)

After Initial Load

![Kafdrop 1](/images/prod/kafdrop1.png)


Now switchback to Qlik Replicate Task manager.
After **Full Load** is complete, click on the `Completed` bar to display the tables. 
There is DML activity running in the background. Click on the `Change Processing` tab to 
see it in action.

> Note: Changes to the tables occur somewhat randomly in the background. You may need to wait a
few minutes before you will see changes appear in the tables that we selected. 

![Kafka Task 10 Image](/images/kafka-task-10.png)

If you would like to see some of the messages we are delivering to Kafka log on to Kafdrop and click on Topics to view the messages.

![Kafka Show Image](/images/prod/kafdrop2.png)

When you have seen enough, you can declare Victory! for this part of the Lab. Press `Stop`
in the top left corner of the **Replicate** console to end the task. 

After pressing `Stop` and clicking 
`Yes` in the confirmation dialog, close the **MySQL to Kafka** tab or click 
on the `TASKS` tab to return to the main window.

![Kafka Task 11 Image](/images/kafka-task-11.png)

### Summary
You just:
* Defined access and authentication into a MySQL source and a Kafka target 
* Defined the source tables from which you want to create Kafka Topics/Messages
* Configured the MySQL to Kafka task
* Captured  initial data from the source without while maintaining business continuity
  (DML activity was going on in the background to simulate users working on the source database)
* Automatically created kafka messages from the initial table state
* Captured all new transactions which were happening while the initial load was running 
* Turned net new data into Kafka messages
* Observed change data being recorded as it is sent to and applied at the  target 

All that in 4 easy steps!

You can now move on to the next part of the AWS Immersive Day [Tutorials](../tutorials).


