
---
title : "Add IAM"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 2. </b> "
---

1. As an AWS administrator: In the AWS Management Console, open the list of all AWS services by choosing Services, and locate and choose `IAM`.
![01](/images/4-add-iam/01.png)

2. In the navigation pane, choose Users and then choose `Add user`.
![02](/images/4-add-iam/02.png)

3. For the User name field, enter: `dude-from-nowhere`.
![03](/images/4-add-iam/03.png)

4. Select AWS Management Console access.
![04](/images/4-add-iam/04.png)

5. For Console password, choose Custom password and enter a password for the dude-from-nowhere user.
6. Clear the `Users must create a new password at next sign-in` check box and choose `Next`.
![05](/images/4-add-iam/05.png)

7. On the Set permissions page, choose Attach existing policies directly.
![06](/images/4-add-iam/06.png)

![07](/images/4-add-iam/07.png)

8. In the Filter policies box, search for and select `AmazonEC2FullAccess` and `AmazonS3FullAccess`, choose `Next`.
![08](/images/4-add-iam/08.png)
![09](/images/4-add-iam/09.png)

9. Review, and then choose `Create user`
![10](/images/4-add-iam/10.png)

10. In the Success page, copy the displayed IAM sign-in URL, and then choose Close. 

