---
title: "Quicksight Visualize"
date: "`r Sys.Date()`"
weight: 8
chapter: false
pre: " <b> 6. </b> "
---

1. As an AWS administrator: In the AWS Management Console, open the list of all AWS services by choosing Services, and locate and choose QuickSight.
   ![01](/images/8-quicksight-visualize/01.png)

2. If this is your first time logging in to QuickSight, you need to sign up for a subscription. To do so, choose Sign up for QuickSight, choose the Standard subscription, and choose Continue.

- **Important**: Remember to unsubscribe from QuickSight after you complete these instructions. You might incur costs from running QuickSight in your account.

3. For QuickSight account name, enter a globally unique name. As a suggestion, you can use <your-initials>-analytics-demo-001 or some other unique value.
   ![02](/images/8-quicksight-visualize/02.png)
   ![03](/images/8-quicksight-visualize/03.png)

4. In the Notification email address box, enter a valid email address.
   ![04](/images/8-quicksight-visualize/04.png) 5. In the following check boxes below, select Amazon S3. A new Select Amazon S3 buckets window will open. In this window, select all the S3 buckets that are related to Athena and CloudTrail and choose Finish.
   ![05](/images/8-quicksight-visualize/05.png)
   ![06](/images/8-quicksight-visualize/06.png)
   ![07](/images/8-quicksight-visualize/07.png)
   ![08](/images/8-quicksight-visualize/08.png)

5. Back in the QuickSight page. Your QuickSight account will be created and ready to use. To start creating visualizations, choose Go to Amazon QuickSight.
   ![09](/images/8-quicksight-visualize/09.png)

6. In the navigation pane, choose Datasets, and in the upper-right area of the screen, choose New dataset.
   ![10](/images/8-quicksight-visualize/10.png)

7. From the data sources list, choose Athena. For Data source name, enter `athena-lab-cloudtrail`, then choose Create data source.
   ![11](/images/8-quicksight-visualize/11.png)
   ![12](/images/8-quicksight-visualize/12.png)

8. Next, choose the Athena table in CloudTrail that you created in the previous step. Choose `Select`. On the next screen, choose Directly query your data and then choose Visualize.
   ![13](/images/8-quicksight-visualize/13.png)
   ![14](/images/8-quicksight-visualize/14.png)

9. In the Fields list, choose eventname. QuickSight will run an Athena query and populate a visualization, which should look like this example.
   ![15](/images/8-quicksight-visualize/15.png)

10. You will now create a new QuickSight dataset that focuses on the actions of the user dude-from-nowhere because you want to get the information that is related to them. In the upper-left corner, choose the QuickSight logo, then from the navigation pane, choose Datasets.
    ![16](/images/8-quicksight-visualize/16.png)

11. Go to the upper-right corner, choose New dataset, then choose Athena. For Data source name, enter `athena-lab-cloudtrail-2` (if not using unique name there will be a conflict) and then choose Create data source.
    ![17](/images/8-quicksight-visualize/17.png)
    ![18](/images/8-quicksight-visualize/18.png)
    ![19](/images/8-quicksight-visualize/19.png)
    ![20](/images/8-quicksight-visualize/20.png)

12. Next, choose Use custom SQL and for the custom SQL query name, enter nicholas-activity. Copy the following query and paste it as the custom SQL query, replacing YOUR-ATHENA-TABLE-HERE with your Athena table name. After you paste and update the SQL, choose `Confirm query`.
    ```SQL
    SELECT *
    FROM
        YOUR-ATHENA-TABLE-HERE
    WHERE 
        eventname LIKE 'StopInstances' AND
        useridentity.username LIKE 'dude-from-nowhere
    ```
    ![21](/images/8-quicksight-visualize/21.png)


13. Choose Directly query your data and then choose Visualize. You now have a dedicated QuickSight dataset that filters for all data under that query scope.
![22](/images/8-quicksight-visualize/22.png)

14. Review the dashboard or choose another chart style to visualize
- To transform that information into a pie chart, go to the navigation pane > Visual types and choose the pie chart icon.
![23](/images/8-quicksight-visualize/23.png)
![24](/images/8-quicksight-visualize/24.png)
![25](/images/8-quicksight-visualize/25.png)
