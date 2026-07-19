## Overview

In this lab, we will configure **Amazon S3** to host a static website and leverage Amazon CloudFront to cache and improve the website's performance.
## 1. Create an S3 Bucket

1-a. Log in to your **AWS account**, navigate to the **S3 console**, and click on **Create Bucket**.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session2/Lab5/image-1.png)

1-b. Set a name for your **S3 bucket** and uncheck the box to **block all public access**. Under **Object Ownership**, select the **ACLs enabled option**. Then, click **Create Bucket**.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session2/Lab5/image-2.png)

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session2/Lab5/image-3.png)

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session2/Lab5/image-4.png)

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session2/Lab5/image-5.png)

## 2. Setup static website hosting

2-a. Download the static website from this URL: [Github - Carlo S3 Website]
](https://github.com/olyvenbayani/S3-Static-Website-Hosting-Labs)

Once the file is downloaded, extract it to get the **index.html** and **badge-camp.png** files.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session2/Lab5/image-6.png)

2-b. Navigate to your **S3 bucket** and click on **Upload**.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session2/Lab5/image-7.png)

2-c. Upload the **index.html** and **badge-camp.png** files to your **S3 bucket**.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session2/Lab5/image-8.png)


2-d. Check the **status** of your file upload to ensure that both **index.html** and **image.jpg** have been successfully uploaded.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session2/Lab5/image-9.png)


2-e. Once the files are uploaded, navigate to the **S3 bucket** and click on **Properties**.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session2/Lab5/image-10.png)

Scroll down to the **Static Website Hosting** section and click to edit the settings.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session2/Lab5/image-11.png)

2-f. Enable **Static Website Hosting** and specify the **index.html** as the index document and error.html (if available) as the error document. If there's no error document, you can leave it blank.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session2/Lab5/image-12.png)

2-g. Retrieve the **static website URL** from the **Static Website Hosting** section in the **S3 bucket properties**. It will be displayed as the **Endpoint URL**.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session2/Lab5/image-13.png)

2-h. The website will not be accessible yet if you try to open the **static website URL** in a browser, as the files need to be publicly accessible first.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session2/Lab5/image-14.png)

2-i. Go back to the **AWS console**, open your **S3 bucket**, select the files you uploaded, then click on **Actions > Make public** to make the files accessible.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session2/Lab5/image-15.png)

- If you cannot select the **Make public using ACL** option, kindly edit **Object Ownership** under **Permissions**. Click on **ACLs enabled** and check the acknowledgement box. 

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session2/Lab5/image-16.png)

- The **Make public using ACL** should now be available

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session2/Lab5/image-17.png)

- Ensure that **index.html** and **image.jpg** are selected, then click on **Make public**.

![](https://sb-next-prod-image-bucket.s3.ap-southeast-1.amazonaws.com/public/CAMP/Labs2025/Session2/Lab5/image-18.png)

2-j. Return to your **web browser** and enter the **static website URL** to access the website.

**Congratulations!** You have successfully hosted a **static website** on an S3 bucket!



Kindly delete all the resources uploaded and used in this laboratory
