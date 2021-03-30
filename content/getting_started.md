
# Preface

Before beginning with the tutorial we like to tell you that your Qlik and AWS team is there to help you please do not hesitate to reach out.

This lab consist of many components to demonstrate for you how easy it is to create connections in Qlik Replicate 

- Stream Data to another Database
- Stream Data to Kafka Queue
- Stream Data into Cloud Data Warehouse 

Inside your aws account a CloudFormation script ran and created a environment where you have a EC2 instance with Docker Compose environment that is running that has SQLPad, MySQL, Postgres, Kafdrop.

Qlik Replicate software is installed on the same EC2 instance with full trial license for your use.

Amazon Redshift Cluster and Sample AWS Bucket is created for your use in this lab.

### Getting access to your lab environment

__By this time all students should have recieved an email from instructor for your server ip address__

# Before starting tutorial and labs make sure you can log into the following:

1. Connecting to Qlik Replicate Web UI
________________________
* url:__https://YOUR_SERVER_IP_ADDRESS:3552/attunityreplicate/__

_This lab has been tested by Firefox Browser and due to certificates not being issued for ephemral servers you will see below warning_

>__Please proceed ahead by pre Clicking `Advanced...` and Pressing `accept risk and proceed on`__

![](/images/prod/warning.png)

Please use the follonwing user name:
* User Name: `admin`
* Password: `Aws_immersion123`  

If you must use a different browser please let the instructor know.

![](/images/prod/logon_replicate.png)


2. Connecting to SQLPad
___
__SQLPad is an Open Source tool that allows user to run SQL Query.__
* url: ___https://YOUR_SERVER_IP_ADDRESS:3000__
* User Name: `admin@qlik.com`
* Password: `Aws_immersion123`  

![](/images/prod/sqlpad.png)

3. Connecting to Kafdrop
___
__Kafdop is an Open Source tool that allows user to view Kafka queue and Topics.__
* url: ___https://YOUR_SERVER_IP_ADDRESS:9000__

![](/images/prod/kafdrop.png)


### Please Click [here](../tutorials) to go to Tutorial.