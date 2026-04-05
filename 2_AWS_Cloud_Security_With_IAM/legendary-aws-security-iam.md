<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Cloud Security with AWS IAM

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-security-iam)

**Author:** Adeem Akhtar  
**Email:** adeemakhtar@gmail.com

---

![Image](http://learn.nextwork.org/satisfied_silver_bold_rose_apple/uploads/aws-security-iam_1c864649)

---

## Introducing Today's Project!

### Project overview

In this project, I will demonstrate Cloud Security using IAM, configure access and permission settings.
I'm doing this project to learn about AWS IAM foundations including IAM User, Groups, and Roles.

### Tools and concepts

Services I used were:
1. EC2 
2. IAM
3. Policy Simulator

Key concepts I learnt include:
1. IAM User
2. IAM Group
3. IAM Roles
4. IAM Policies
5. IAM policy testing

### Project reflection

This project took me approximately 45 minutes. The most challenging part was understanding IAM policy JSON syntax. It was most rewarding to learn parts of policies and syntax.

---

## Tags

### What I did in this step

In this step, I will launch 2 Amazon EC2 instances to boost NextWork's computing power. We are expecting more users and traffic on the website during summer break.

### Understanding tags

Tags are organisational tools for resource labelling. They help group the resources and cost allocation to the similar tagged resources.

### My tag configuration

The tag I’ve used on my EC2 instances is called "env" The values I’ve assigned for my instances are "production" and "development"

![Image](http://learn.nextwork.org/satisfied_silver_bold_rose_apple/uploads/aws-security-iam_2e0e5a5d)

---

## IAM Policies

### What I did in this step

In this step, I will use IAM policies to control the access level of the new intern because they should have access to the development environment but not the production environment. 

### Understanding IAM policies

IAM Policies are rules that determine who can do what.

### The policy I set up

For this project, I’ve set up a policy using JSON editor in IAM.

### Policy effect

I’ve created a policy that allow the policy holder to have permission to do anything they want to any instance tagged as development.
they can also see information related to any instance but they are denied access to creating and deleting tags.

### Understanding Effect, Action, and Resource

The Effect, Action, and Resource attributes of a JSON policy mean:
Allowing/denied action (Effect),
What the policy holder can do/cannot do to the AWS resource (Action), 
and the specific policy related to (Resource)

---

## My JSON Policy

![Image](http://learn.nextwork.org/satisfied_silver_bold_rose_apple/uploads/aws-security-iam_1c864649)

---

## Account Alias

### What I did in this step

In this step, I will set up an account alias. which is like a nickname of our AWS account console login. This is because an account alias makes it simpler for our users to login.

### Understanding account aliases

An account alias is a unique URL that can be used to access the account using the correct credentials. 

### Setting up my account alias

Creating an account alias took me a few clicks from the IAM dashboard.

![Image](http://learn.nextwork.org/satisfied_silver_bold_rose_apple/uploads/aws-security-iam_0eb4439b)

---

## IAM Users and User Groups

### What I did in this step

In this step, I will create a group "nextwork-dev-group" and assign it the permission policy that I created "NextWorkDevEnvironmentPolicy".

### Understanding user groups

IAM user groups are collections of users with dedicated permissions in AWS. 

### Attaching policies to user groups

I attached the policy I created to this user group, which means the users within the group are allowed to do anything with the "development" instance, along with the view of all other instances' descriptions in the account, but are denied access to the "production" instance.

### Understanding IAM users

IAM users are the individuals who are assigned permissions directly or through groups that define what they are allowed/denyed to do in the AWS account.

---

## Logging in as an IAM User

### Sharing sign-in details

The first way is to send them the email including the credentials directly.
Secondly, give them through written documentation. 

### Observations from the IAM user dashboard

Once I logged in as my IAM user, I noticed there is a console walkthrough. This was because the intern had logged in for the first time.
Secondly, there are many services that are restricted for interns as they are denied in the attached group policy.

![Image](http://learn.nextwork.org/satisfied_silver_bold_rose_apple/uploads/aws-security-iam_6f2ab446)

---

## Testing IAM Policies

### What I did in this step

In this step, I will sign in to the AWS account as an intern's IAM user because I have to test the account permissions "Are they working as they are supposed to?"

### Testing policy actions

I tested my JSON IAM policy by stopping the development instance as well as the production instance. In case of a development instance, the instance stopped, but in case of a production instance, the instance gave an error.

### Stopping the production instance

When I tried to stop the production instance, it gave an error. This was because of the denied permission in the attached group policy.

![Image](http://learn.nextwork.org/satisfied_silver_bold_rose_apple/uploads/aws-security-iam_0e7a9d6a)

### Stopping the development instance

Next, when I tried to stop the development instance, the instance stopped due to the allowed permission in the policy,

![Image](http://learn.nextwork.org/satisfied_silver_bold_rose_apple/uploads/aws-security-iam_1811801c)

---

## IAM Policy Simulator

To extend my project, I'm going to use the "Policy Simulator" tool.  I'm doing this because I want to verify if my assigned policy is working as it is supposed to. It's a handy tool that can be used from the admin login without logging into the intern account login.

### Understanding the IAM Policy Simulator

The IAM Policy Simulator is testing tool for verifying the policies permission.

### How I used the simulator

I set up a simulation for the intern account for "development as well as production" instances. Initially, the results showed that both instances' access is denied for the intern, but after adjusting the simulator on the development instance, the access turns into "allowed"

![Image](http://learn.nextwork.org/satisfied_silver_bold_rose_apple/uploads/aws-security-iam_069d8a621)

---

---
