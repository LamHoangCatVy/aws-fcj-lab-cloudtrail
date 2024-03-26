---
title : "CloudTrail Configuring"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 1. </b> "
---


1. As an AWS administrator: In the AWS Management Console, open the list of all AWS services by choosing Services, and then locate and choose CloudTrail.
![01](/images/3-cloudtrail/01.png)
2. Choose Create trail in the CloudTrail dashboard
![02](/images/3-cloudtrail/02.png)
Or choose `Trails` -> `Create Trail`
![03](/images/3-cloudtrail/03.png)
3. For Trail name, enter default. If that Trail name already exists in your account, enter: `lab-data-cloudtrail-default`
4. In the Trail log bucket and folder box, keep the default name suggestion. Note that this S3 bucket is the bucket where CloudTrail will store information. Make sure that you copy this bucket name in Notepad or some places because you will need it when you create the Amazon Athena table in later part.
5. Clear the **Log file SSE-KMS** encryption check box.
![04](/images/3-cloudtrail/04.png)
6. Scroll to the bottom of the page and choose `Next`.
![05](/images/3-cloudtrail/05.png)
7. On the next page, select **Management events**, **Data events**, and **Insights events**.
![06](/images/3-cloudtrail/06.png)
8. In the Data event, at:
- Data event type: choose `S3`
- Log selector template: choose `Log all events`
- Selector name - optional: type `lab-data-events log` to clarify
![07](/images/3-cloudtrail/07.png)
9. In the Insights events section, tick `API call rate` and `API error rate`, then click `Next`
![08](/images/3-cloudtrail/08.png)
10. Review and Scroll down
![09](/images/3-cloudtrail/09.png)
11. Click `Create trail`
![10](/images/3-cloudtrail/10.png)
12. You can click the S3 bucket link to see the objects created automatically by CloudTrail
![11](/images/3-cloudtrail/11.png)
13. You now have a new CloudTrail dataset that is being created in the designated bucket. You can go to Amazon S3 and inspect how the data structure will look like. As you interact with the AWS Management Console, your user is issuing API calls, which are captured and stored by CloudTrail.
![12](/images/3-cloudtrail/12.png)

