---
title : "Building a Simple AWS CloudTrail Data Analytics Solution"
date : "`r Sys.Date()`"
weight : 1
chapter : false
---

# Building a Simple AWS CloudTrail Data Analytics Solution

#### Overview

The demo will show how you can visualize AWS CloudTrail data in Amazon QuickSight and start building simple security dashboards. Although CloudTrail is enabled by default in every AWS Account, Kathy (me) will configure a new trail, and also to show where CloudTrail configurations are made.

After configuring a new trail, I will add a new user into my AWS account (named dude-from-nowhere). I will then log in as that user and do some activity that simulates a user who is issuing application programming interface (API) calls. One of these API calls will (accidentally) turn off a web server. If you want to follow the exact instructions in your account, you can mimic the scenario that I has in this account before you enable CloudTrail. To do so, you can create an Amazon Elastic Compute Cloud (Amazon EC2) instance to function as the web server.

After I turns off the web server as the user `dude-from-nowhere`, I will log out and log in again as an administrator. I will then use CloudTrail data to investigate what happened by getting information, such as when the server was turned off. I will also discover the other API calls that the nicholas user made, because that account could have been compromised.

Here is the reference architect for this lab
![architect](/images/architect/lab-cloudtrail-architect.png)
#### Content

<!-- 1. [Introduction](1-services-theory/)
2. [Prerequisites](2-prerequisites/) -->
1. [Configuring CloudTrail](3-config-cloudtrail/)
4. [Add a secondary IAM User](4-add-iam/)
5. [Create EC2 Instance](5-add-ec2/)
6. [Using `dude-from-nowhere` to Stop Instance](6-stop-ec2/)
7. [Query CloudTrail data in Amazon Athena](7-athena-query/)
8. [Visualizing Athena data in QuickSight](8-quicksight-visualize/)
9. [Resources Clean Up](9-clean-up)