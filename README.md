**Assignment: Create an EC2 Instance and Deploy Nginx**
**Objective**

To learn basic AWS and DevOps concepts by creating an EC2 instance, connecting to it using SSH, installing Nginx, and accessing it via a web browser on port 80.

**Prerequisites**

AWS account

Basic knowledge of Linux commands

SSH client (Terminal / Git Bash / PuTTY)

**Step 1: Launch an EC2 Instance**

Log in to AWS Management Console

Navigate to EC2 → Instances → Launch Instance

Choose an Amazon Machine Image (AMI)

Example: Amazon Linux 2

Choose an Instance Type

Example: t2.micro (Free Tier eligible)

Create or select a Key Pair

Download the .pem file

Configure Security Group

Allow SSH (Port 22) – Source: My IP

Allow HTTP (Port 80) – Source: Anywhere (0.0.0.0/0)

Click Launch Instance

**Step 2: Connect to EC2 Using SSH**

Copy the Public IPv4 Address of the EC2 instance

Open terminal and run:

chmod 400 your-key.pem
ssh -i your-key.pem ec2-user@<public-ip>


✅ Successfully connected to the EC2 instance

**Step 3: Update the Server**
sudo yum update -y

Step 4: Install Nginx
sudo amazon-linux-extras install nginx1 -y


or (if using Ubuntu):

sudo apt update
sudo apt install nginx -y

Step 5: Start and Enable Nginx
sudo systemctl start nginx
sudo systemctl enable nginx


**Verify status:**

sudo systemctl status nginx

Step 6: Open Port 80 in Security Group

Go to EC2 → Security Groups

Edit Inbound Rules

Add rule:

Type: HTTP

Port: 80

Source: Anywhere (0.0.0.0/0)

Step 7: Access Nginx from Browser

Open a web browser

Enter:

http://<public-ip>


**✅ Nginx default page is displayed successfully**

**Outcome**

Successfully launched an EC2 instance

Connected via SSH

Installed and configured Nginx

Exposed the application on port 80

Verified access via browser

**Tools & Technologies Used**

AWS EC2

Linux

SSH

Nginx


This assignment helped me understand basic AWS infrastructure, Linux server management, and web server deployment. It demonstrates foundational DevOps skills such as cloud provisioning, service configuration, and networking.
