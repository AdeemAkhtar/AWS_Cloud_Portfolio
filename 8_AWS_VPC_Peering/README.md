<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# VPC Peering

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-peering)

**Author:** Adeem Akhtar  
**Email:** adeemakhtar@gmail.com

---

## VPC Peering
![<# alt text #>](Architecture.png "Screenshot")
![Image](http://learn.nextwork.org/satisfied_silver_bold_rose_apple/uploads/aws-networks-peering_88727bef)

---

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC is an isolated private network in the cloud and it is useful because we can arrange our resources in it.

### How I used Amazon VPC in this project

In today's project, I used Amazon VPC to communicate with another VPC through peering connection.

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was connecting two VPCs was this easy.

### This project took me...

This project took me 30 minutes.

---

## In the first part of my project...

### Step 1 - Set up my VPC

In this step, I will create two VPCs from scratch using the resource map because it will save time.

### Step 2 - Create a Peering Connection

In this step, I will create a VPC Peering connection link because we need both of the VPCs to be connected together for communication.

### Step 3 - Update Route Tables

In this step, I will set up the route table for the incoming and outgoing traffic between VPC 1 and VPC 2....

### Step 4 - Launch EC2 Instances

In this step, I will test the peered VPCs by launching and connecting the EC2 in both of the VPCs.

---

## Multi-VPC Architecture

I started my project by launching VPC using the resource map. I launched 1 public subnet per VPC.

The CIDR blocks for VPCs 1 and 2 are 10.1.0.0/16 and 10.2.0.0/16. They have to be unique because each VPC has to have a unique IP address. Providing each other with a different range of IPs will discourage IP overlapping.  

### I also launched 2 EC2 instances

I didn't set up key pairs for these EC2 instances as WS actually manages a key pair for us! We don't need to manage key pairs ourselves. 

![Image](http://learn.nextwork.org/satisfied_silver_bold_rose_apple/uploads/aws-networks-peering_11111111)

---

## VPC Peering

A VPC peering connection is a direct connection between two VPCs.
A peering connection lets VPCs and their resources route traffic between them using their private IP addresses. This means data can now be transferred between VPCs without going through the public internet.

VPCs would use peering connections to provide the connection on which the vpc can be connected together and start the communication.

The difference between a Requester and an Accepter in a peering connection is that the Requester is the VPC that requests to be connected to the connecting VPC, whereas the Accepter is the VPC that accepts or rejects the request of connection from the Requester.

![Image](http://learn.nextwork.org/satisfied_silver_bold_rose_apple/uploads/aws-networks-peering_1cbb1b88)

---

## Updating route tables

After accepting a peering connection, my VPCs' route tables need to be updated because route tables are the only way through which they will be able to know to how to get the to the resources even in the different VPCs.

My VPCs' new routes have a destination of VPC 1 (10.1.0.0/16). The routes' target was Peering Connection on the VPC peering. 

![Image](http://learn.nextwork.org/satisfied_silver_bold_rose_apple/uploads/aws-networks-peering_4a9e8014)

---

## In the second part of my project...

### Step 5 - Use EC2 Instance Connect

In this step, I will use EC2 in VPC 1 to test the connectivity. 

### Step 6 - Connect to EC2 Instance 1

In this step, I will fix the error that says there is an error with the connection establishment with SSH. 

### Step 7 - Test VPC Peering

In this step, I will get Instance 1 to send test messages to Instance 2 because I have to test the connection with EC2 in VPC 2.

---

## Troubleshooting Instance Connect

Next, I used EC2 Instance Connect to get connected with the EC2 using SSH.

I was stopped from using EC2 Instance Connect as public IPv4 was not associated with that EC2.

![Image](http://learn.nextwork.org/satisfied_silver_bold_rose_apple/uploads/aws-networks-peering_7685490c)

---

## Elastic IP addresses

To resolve this error, I set up Elastic IP addresses. Elastic IP addresses are static IPs that could be associated to the EC2. This static could perform as public IP.

Associating an Elastic IP address resolved the error because after associating the Elastic IP with the EC2 acted as a public IP.

![Image](http://learn.nextwork.org/satisfied_silver_bold_rose_apple/uploads/aws-networks-peering_45663498)

---

## Troubleshooting ping issues

To test VPC peering, I ran the command 'ping'

A successful ping test would validate my VPC peering connection because it received the answer of its connection request.

I had to update my second EC2 instance's security group because ICMP rule was not configured. I added a new rule that ALL ICMP to Anywhere IPv4.

![Image](http://learn.nextwork.org/satisfied_silver_bold_rose_apple/uploads/aws-networks-peering_7a29d352)

---

---
