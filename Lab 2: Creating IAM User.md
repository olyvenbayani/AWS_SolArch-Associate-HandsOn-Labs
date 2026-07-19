# Lab 2: Creating IAM User

## Overview

AWS Identity and Access Management (IAM) allows you to effectively manage access to AWS services and assets for your user base, ensuring a high level of security. This service is designed for organizations that have numerous users or systems utilizing AWS services like Amazon EC2, Amazon RDS, and the AWS Management Console. IAM offers centralized user management, the administration of security credentials like access keys, and the regulation of permissions that determine users' access to AWS resources.

In this hands-on lab, you will establish an IAM user for your lab partner, granting them specific access to your personal AWS environment. Your partner will do the same for you.

*(Prerequisite: Before starting, ensure you have created at least one S3 bucket in your account and uploaded a test file into it so your partner has something to interact with.)*

## 1. Creating an IAM User for Your Lab Partner

**1-a.** From the AWS Management Console, search for **IAM**.

![Step 1a - Search for IAM](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/GENC-Lab01/1-a.jpg)

**1-b.** On the Access management tab on the left-hand menu, choose **Users**.

![Step 1b - Choose Users](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/GENC-Lab01/1-b.jpg)

**1-c.** Create a user by clicking the **Create user** button on the console.

![Step 1c - Create User](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/GENC-Lab01/1-c.jpg)

**1-d.** Enter the user name of the IAM User you are creating (e.g., `partner-[PartnerName]`). This will be used by your lab partner to log in to your AWS Management Console.

![Step 1d - Enter User Name](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/GENC-Lab01/1-d.jpg)

**1-e.** Set the permissions for the IAM User by choosing **Attach policies directly**. IAM Policies are sets of rules and permissions that determine what actions users, groups, and roles are allowed to perform on AWS resources. These policies help in controlling and managing access to AWS services securely.

**1-f.** Search for and select **AmazonS3ReadOnlyAccess** on the permission policies list. This restricts your partner to only viewing your S3 resources without the ability to modify or delete them. Click **Next**, review the details, and click **Create user**.

![Step 1e - Attach Policies](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/GENC-Lab01/1-e.jpg)

## 2. Enabling Your Partner's Access to the Console

**2-a.** Once back on the IAM Users Page, click on the user profile you recently created for your partner.

![Step 2a - Select User](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/GENC-Lab01/2-a.jpg)

**2-b.** Choose the **Security credentials** tab and click **Enable console access**.

![Step 2b - Enable Console Access](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/GENC-Lab01/2-b.jpg)

**2-c.** Choose to enable console access for the user. Select **Custom password** and create a secure password to share with your partner. Tick the box that says **Users must create a new password at next sign-in** to ensure their access remains private and secure.

![Step 2c - Console Access Options](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/GENC-Lab01/2-c.jpg)

**2-d.** Click **Apply** and wait for the confirmation that the user's password is enabled. **Important:** Download the `.csv` file or copy the **Console sign-in URL**, **Username**, and **Password**. Share these three pieces of information securely with your lab partner so they can access your account.

![Step 2d - Apply Password](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/GENC-Lab01/2-d.jpg)

## 3. Signing In as the IAM User (Testing Your Partner's Account)

*(For this section, swap roles. You will now use the credentials your partner provided to log into their AWS account, while they log into yours.)*

**3-a.** Using the **Console sign-in link** provided by your partner, open a new incognito/private browser tab. Fill in the **Account ID** (usually pre-filled by the link), the **IAM user name**, and the **Password** your partner gave you. Click the **Sign in** button. If prompted, create a new password.

![Step 3a - Console Sign-in Link](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/GENC-Lab01/3-a.jpg)

![Step 3a - Sign In](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/GENC-Lab01/3-b.jpg)

**3-b.** Once logged in, notice that the username is displayed on the top right of the AWS Management Console (e.g., `partner-yourname @ Partner-Account-ID`). This proves that you are currently signed in as the IAM User in your partner's environment.

**3-c.** Search for and navigate to **Amazon S3**.

![Step 3c - Navigate to S3](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/GENC-Lab01/3-c.jpg)

![Step 3c - S3 Console](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/GENC-Lab01/3-d.jpg)

**3-d.** Look for the test bucket your partner created prior to this lab. Click on the bucket, select the test file inside, and click **Delete**.

![Step 3d - Find Bucket](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/GENC-Lab01/3-d2.jpg)

**3-e.** **Verification:** If the lab was set up correctly by your partner, you will receive an "Access Denied" or "Insufficient Permissions" error when attempting to delete the object. This confirms that the IAM policy successfully enforced read-only access to their S3 bucket.
