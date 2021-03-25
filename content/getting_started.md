
# Preface

Before beginning with the tutorial we like to tell you that your Qlik and AWS team is there to help you please do not hesitate to reach out.

This lab consist of many components to demonstrate for you how easy it is to create connections in Qlik Replicate 

- Stream Data to another Database
- Stream Data to Kafka Queue
- Stream Data into Cloud Data Warehouse 

Inside your aws account a CloudFormation script ran and created a environment where you have a EC2 instance with Docker Compose environment that is running that has SQLPad, MySQL, Postgres, Kafdrop.

Qlik Replicate software is installed on the same EC2 instance with full trial license for your use.

Amazon Redshift Cluster and Sample AWS Bucket is created for your use in this lab.

# You should ask the instructor for your server ip address or check in CloudFormation console for information.

__Before starting tutorial and labs make sure you can log into the following__ 

### Instruction for this Lab
______________________
* url: __http://your_host_ip__  

![](/images/prod/instructions.png)

### Connecting to Qlik Replicate Web UI
________________________
_This lab has been tested by  Firefox Browser and you need click `Advanced...` and accept risk due to certificates_

![](/images/prod/warning.png)

* url:___https://your_host_ip:3552/attunityreplicate/_
* User Name: `admin`
* Password: `Aws_immersion123`  

![](/images/prod/logon_replicate.png)

__For the lab we will not be using a certificate rather we will 'accept risk and proceed on'__

### Connecting to SQLPad
___
__SQLPad is an Open Source tool that allows user to run SQL Query.__
* url: ___https://your_host_ip:3000_
* User Name: `admin@qlik.com`
* Password: `Aws_immersion123`  

![](/images/prod/sqlpad.png)

### Connecting to Kafdrop
___
__Kafdop is an Open Source tool that allows user to view Kafka queue and Topics.__
* url: ___https://your_host_ip:9000_

![](/images/prod/kafdrop.png)


# [Please Click here to go to Tutorial](../tutorials) 