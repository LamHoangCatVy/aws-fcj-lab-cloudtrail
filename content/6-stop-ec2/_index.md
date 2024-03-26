---
title : "Using dude-from-nowhere to Stop EC2 Instance"
date :  "`r Sys.Date()`" 
weight : 6
chapter : false
pre : " <b> 4. </b> "
---

1. Remember you have a secondary IAM user (dude-from-nowhere) that has the permissions to fully interact with Amazon EC2 and Amazon S3. Let's log in as the new dude-from-nowhere user by using the sign-in URL.
![02](/images/6-stop-ec2/02.png)

2. You can verify if you are logged in with the dude-from-nowhere user by looking in the upper-right are of the AWS Management Console. 
3. Choose the region that aligns with the one in which you've created your EC2 instance
![03](/images/6-stop-ec2/03.png)

3. Navigate to EC2 service, and stop the instance as the following steps.
- In the `dude-from-nowhere` account, you'be issued some API calls by navigating through the AWS Management Console. All your actions are captured by CloudTrail.

- While you are logged in to the console as `dude-from-nowhere`, shut down an EC2 instance. Before you shut down any EC2 instances, make sure that you don’t need them, or that you created an additional EC2 instance specifically for this exercise.

![04](/images/6-stop-ec2/04.png)
![05](/images/6-stop-ec2/05.png)
![06](/images/6-stop-ec2/06.png)


Log out as dude-from-nowhere and log back in as the administrator because you will next use Amazon Athena to query CloudTrail data!

![07](/images/6-stop-ec2/07.png)
![08](/images/6-stop-ec2/08.png)
