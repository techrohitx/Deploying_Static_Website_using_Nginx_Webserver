# Deploying Static Website on AWS EC2 using nginx Webserver

## :round_pushpin: Introduction ##

This project represents the process of deploying a static website on Amazon Linux EC2
instance using nginx webserver. The process includes how to set up a server, configure a 
web server, and make their website accessible to the public.

## :dart: Prerequisites

Before getting started, make sure you have:
1. An AWS account
2. Amazon linux EC2 instance
3. SSH key pair
4. A static website files ready for deployment.

## :bulb: Deployment Steps

### **Step 1: Launch EC2 instance** :rocket:

1. select AMI - Amazon Linux 2 and name for that instance
2. select instance type - t3.micro for free tier
3. If you already have a SSH key pair then select it otherwise create a new one.
4. Create a security group and allow SSH traffic (port 22) and HTTP traffic (port 80)
5. Click on Launch Instance.
![Reference Image](/img/St-1.png)

### **Step 2: Copying Static Website files from local machine to EC2** :clipboard:

```bash
scp -i <private-key> -r <folder_name/> ec2-user@public_IP:/home/ec2-user
# to copy folder from local machine to EC2
```
![Reference Image](/img/St-2.png)

### **Step 3: Connect to the Instance** :key:




```bash
sudo yum update
sudo yum install nginx -y
sudo systemctl start nginx
sudo systemctl enable nginx
sudo systemctl status nginx
```
![Reference Image](/img/s-3.png)

### **Step 4: Access the website** :globe_with_meridians:

**Open a browser and hit your EC2 public IP to view the website.**
![Reference Image](/img/S-4.png)
![Reference Image](/img/S-5.png)

## :pushpin:**Summary**

This project covers a detailed how-to for setting up a static website on Amazon Linux EC2.
Launching an EC2 instance, installing and configuring a web server (nginx), setting up
security groups with the required inbound rules, and releasing website files for the public
to view are all described. This is the first time I have successfully deployed a website from
start to end in the cloud.


