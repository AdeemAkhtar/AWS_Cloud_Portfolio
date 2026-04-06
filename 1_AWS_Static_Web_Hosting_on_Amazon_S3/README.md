<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Host a Website on Amazon S3

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-host-a-website-on-s3)

**Author:** Adeem Akhtar  
**Email:** adeemakhtar@gmail.com

---

![Image](http://learn.nextwork.org/satisfied_silver_bold_rose_apple/uploads/aws-host-a-website-on-s3_5d4474f9)

---

## Introducing Today's Project!

### Project overview

In this project, I demonstrate how to host a static website using Amazon S3 via the AWS Management Console. This project forms part of my practical learning in Cloud Computing, allowing me to develop hands-on experience with AWS services and deployment processes.

### Tools and concepts

Services I used were Amazon S3.
Key concepts I learnt include using S3 bucket as web hosting, making the objects public, and restricting access using ACLs.

### Time, challenges, and wins

This project took me approximately 40 minutes. The most challenging part was understanding the policy json code. It was most rewarding to practice using S3.

---

## How I Set Up an S3 Bucket

### What I did in this step

In this step, I will ...
1. Open Amazon S3 by searching for and selecting it from the search results. 
2. Create a new general-purpose S3 bucket and store static website files in it.

### How long it took to create the bucket

Creating an S3 bucket took me just 2 - 3 minutes, considering it for the first time.

### Region selection

The Region I picked for my S3 bucket was Oregon
us-west-2 because that is closest to my operating location.

### Understanding bucket name uniqueness

S3 bucket names are globally unique! This means the bucket should be globally unique, so it should have a name that is not already available anywhere.

![Image](http://learn.nextwork.org/satisfied_silver_bold_rose_apple/uploads/aws-host-a-website-on-s3_ba6d42ad)

---

## Upload Website Files to S3

### What I did in this step

In this step, I will download the HTML file and zip file.
Will upload in the S3 bucket

### Files I uploaded

I uploaded two files to my S3 bucket - they were 
1. index.html
2. Folder with asserts

### How the files work together

Both files are necessary for this project as index.html organises the data on the web page. The other folder contains all the asserts (data).

![Image](http://learn.nextwork.org/satisfied_silver_bold_rose_apple/uploads/aws-host-a-website-on-s3_a265af88)

---

## Static Website Hosting on S3

### What I did in this step

In this step, I will configure our S3 bucket so it can host the static website and let the public visit the website with the website link.

### Understanding website hosting

Website hosting means making the website public on internet so the user could access.

### How I enabled website hosting

To enable website hosting with my S3 bucket, I edited the S3 static hosting properties.

### Access Control Lists (ACLs)

An ACL is a set of rules that decides who can access the s3 bucket and objects inside. We will enable the ACLs as we will be using ACL to manage the access permissions.

![Image](http://learn.nextwork.org/satisfied_silver_bold_rose_apple/uploads/aws-host-a-website-on-s3_c22c54c0)

---

## Bucket Endpoints

### Understanding bucket endpoint URLs

Once static website is enabled, S3 produces a bucket endpoint URL, which is the url that could be used to access the website.

### What I saw when I tested the endpoint

When I first visited the bucket endpoint URL, I saw a 403 error, which is a permission denial server error. The reason for this error was that the file (objects) uploaded to S3 are still private.

![Image](http://learn.nextwork.org/satisfied_silver_bold_rose_apple/uploads/aws-host-a-website-on-s3_22ce4daf)

---

## Success!

### What I did in this step

In this step, I will make the objects public because the content has to be accessed over the internet publicly. 

### How I resolved the 403 error

To resolve this 403 Forbidden error, I made the S3 object public.

![Image](http://learn.nextwork.org/satisfied_silver_bold_rose_apple/uploads/aws-host-a-website-on-s3_5d4474f9)

---

## Bucket Policies

### What I did in this extension

In this project extension, I'm about to set up a bucket policy. I'm doing this to stop people from deleting index.html

### Understanding bucket policies

An alternative to Access Control Lists (ACLs) are bucket policies, which are JSON-based access control mechanisms used to define permissions for an entire Amazon S3 bucket and its objects. Bucket policies allow you to grant or restrict access to specific users, accounts, or services using structured and scalable rules.

The benefit of using bucket policies is that they provide centralised, flexible, and fine-grained control over access permissions, making them easier to manage for complex or large-scale configurations. They also support advanced conditions, such as restricting access based on IP address or enforcing secure (HTTPS) connections.

In contrast, ACLs are useful for simpler, object-level permissions, particularly when you need to grant basic read or write access to individual objects or make content publicly accessible in a straightforward way.

![Image](http://learn.nextwork.org/satisfied_silver_bold_rose_apple/uploads/aws-host-a-website-on-s3_sm2sm2sm)

### What my bucket policy does

My bucket policy prohibits the deletion of the index.html object in my S3 bucket.
I tested this by deleting the index.html and saw a pop-up appear saying "failed to delete object".

---

---
