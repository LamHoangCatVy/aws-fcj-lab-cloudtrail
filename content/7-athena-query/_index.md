---
title : "Athena Query"
date :  "`r Sys.Date()`" 
weight : 7
chapter : false
pre : " <b> 5. </b> "
---

## Scenario
People in your organization are saying that a web server was turned off and the website is now offline. Now, you will use CloudTrail data to investigate what happened and get evidence of the action, including:

- Who shut down the web server
- When they shut it down
- Where they shut it down from
You will do this investigation by creating an Athena table that points to the S3 bucket that is used by your new CloudTrail configuration.

1. As an AWS administrator: In the AWS Management Console, open the list of all AWS services by choosing Services, and locate and choose CloudTrail.
![01](/images/7-athena-query/01.png)

2. In the navigation pane, choose Event history, and then choose Create Athena table
![02](/images/7-athena-query/02.png)

3. In Storage location, choose the bucket you created as part of CloudTrail configuration. This action will update the structured query language (SQL) command that creates the table to use the corresponding bucket location
4. Choose `Create table`
![03](/images/7-athena-query/03.png)

You now have an Athena table with the same schema that is used by CloudTrail. The table points to the recently created S3 bucket that is used by CloudTrail.

5. As an AWS administrator: In the AWS Management Console, open the list of all AWS services by choosing Services, and locate and choose Athena.
![04](/images/7-athena-query/04.png)

6. If this is the first time you’re using Athena in this AWS account, you will need configure some settings. In the upper-right area of the window, choose Settings.
![05](/images/7-athena-query/05.png)

7. Then, select another S3 bucket for the Athena query result location by choosing the Select button. A bucket might have been automatically created for this purpose, so you might only need to select a bucket with a name that starts with aws-athena-query-results, click `Choose`
![06](/images/7-athena-query/06.png)

8. After you select the bucket, choose Save, and you are ready to do Athena queries.
![07](/images/7-athena-query/07.png)
![08](/images/7-athena-query/08.png)

10. To get the activity history of a given EC2 instance, run the following query. Make sure to replace the instance ID with your instance ID. You also need to replace YOUR-ATHENA-TABLE-HERE with the name of your Athena table. You can copy the table name from the navigation pane. The query looks like this example:
```SQL
SELECT *
FROM
    YOUR-ATHENA-TABLE-HERE
WHERE 
    eventname LIKE 'StopInstances' AND
    useridentity.username LIKE 'dude-from-nowhere'
```
10. Click `Run`.
![09](/images/7-athena-query/09.png)
11. Scroll down and review the query.
![10](/images/7-athena-query/10.png)
