# certificate-of-course-completion-on-AWS

HOSTING A STATIC WEBSITE.

Task 1: Creating a bucket in Amazon S3
In this task, you create an S3 bucket and configure it for static website hosting.

In the AWS Management Console, on the Services menu, choose S3.

Choose Create bucket

An S3 bucket name is globally unique, and all AWS accounts share the namespace. After you create a bucket, no other AWS accounts in any AWS Regions can use the name of that bucket unless you delete the bucket.

For this lab, you use a bucket name that includes a random number, such as website-123.

For Bucket name, enter website-<123> and replace <123> with a random number.

Public access to buckets is blocked by default. Because the files in your static website will need to be accessible through the internet, you must permit public access.

For Object Ownership, choose ACLs enabled.

Choose Bucket owner preferred.

For Block Public Access settings for this bucket, clear the check box for Block all public access, and then select the box that states I acknowledge that the current settings might result in this bucket and the objects within becoming public.

For Bucket Versioning, choose Enable.

Note: Once you turn on (enable) bucket versioning, you can't turn it off.

For Tags, choose Add tag, and enter the following:

Key: Department
Value: Marketing
You can use tags to add additional information to a bucket, such as a project code, cost center, or owner.

Choose Create bucket

In the Buckets section, choose the name of your new bucket.

Choose the  Properties tab.

 

Task 2: Configuring a static website on Amazon S3
   You will now configure the bucket for static website hosting.

Scroll to the Static website hosting panel.

Choose Edit

Configure the following settings:

Static web hosting: Choose Enable.
Hosting type: Choose Host a static website.
Index document: Enter index.html
Error document: Enter error.html
Note: You must enter index.html and error.html even though they are already displayed.

Choose Save changes

In the Static website hosting panel under Bucket website endpoint, choose the link.

You receive a 403 Forbidden message because you have not yet configured the bucket permissions. Keep this tab open in your web browser so that you can return to it later.

You have configured your bucket to host a static website.


Task 3: Uploading content to your bucket
In this task, you upload the static files to your bucket.

Choose (right-click) each of the following links, and download the files to your computer:
    Ensure that each file keeps the same file name, including the extension.

index.html
script.js
style.css
Return to the Amazon S3 console, and choose the Objects tab.
Choose Upload
Choose Add files
Choose the three files that you downloaded.
Choose Upload
   Your files are uploaded to the bucket.

Choose Close

Task 4: Turning on public access to the objects
Objects that are stored in Amazon S3 are private by default. This setting helps keep your organization's data secure.

In this task, you make the uploaded objects publicly accessible so users can view your website.

First, confirm that the objects are currently private.

Return to the browser tab that showed the 403 Forbidden message.
Refresh  the webpage.
    If you accidentally closed this tab, go to the Properties tab, and in the Static website hosting panel, choose the Bucket website endpoint link again.

   You should still see a 403 Forbidden message. This response is expected! This message indicates that your static website is being hosted by Amazon S3 but that the content is private.

   You can make Amazon S3 objects public through two different ways:

To make either a whole bucket public or a specific directory in a bucket public, use a bucket policy.
To make individual objects in a bucket public, use an access control list (ACL).
   It is normally safer to make individual objects public because doing so avoids accidentally making other objects public. However, if you know that the entire bucket contains no sensitive information, you can use a bucket policy.

   You now configure the individual objects to be publicly accessible.

Keep the website tab open, and return to the web browser tab with the Amazon S3 console.
Choose  all three objects.
In the Actions menu, choose Make public using ACL.
   A list of the three objects is displayed.

Choose Make public
   Your static website is now publicly accessible.

Choose Close
Return to the web browser tab that has the 403 Forbidden message.
Refresh  the webpage.
   You should now see the static website that is being hosted by Amazon S3.


Now you know how to share objects with everyone by making them public. However, there may be times when you need to share an individual object for a limited amount of time. In the next task, you learn how to temporarily share an object.
