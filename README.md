# Simple HTML profile page Deployment with Apache on EC2

This project demonstrates how to deploy a simple HTML profile page on an AWS EC2 instance using Apache. The setup and deployment process>

## Table of Contents

- [Prerequisites](#prerequisites)
- [Setup](#setup)
  - [Launch an EC2 Instance](#launch-an-ec2-instance)
  - [Connect Using MobaXterm](#connect-using-mobaexterm)
  - [Install Apache](#install-apache)
  - [Deploy the HTML File](#deploy-the-html-file)
- [Conclusion](#conclusion)

## Prerequisites

- AWS account with an EC2 instance running Ubuntu
- MobaXterm for SSH and SCP operations

## Setup

### Launch an EC2 Instance

1. **Create an EC2 instance** running Ubuntu on AWS.
2. **Download the PEM key** for SSH access.

### Connect Using MobaXterm

1. **Open MobaXterm**.
2. **Start a new SSH session**:
   - Click on `Session`.
   - Select `SSH`.
   - Enter the public IP address of your EC2 instance.
   - Use `ubuntu` as the username.
- For the key, browse and select your downloaded PEM key file.
   - Click `OK` to connect.

1. **Update your package list**:
   ```bash
   sudo apt update
   sudo apt install apache2 -y
   sudo systemctl start apache2

### Deploy the website
1. **Create an HTML file on your local machine named "index.html"
2. **Upload the html file to your ec2 instance
   - in MobaXterm, use the SFTP browser panel on the left side.
   - Navigate to '/var/www/html/'
   - Use the 'Upload to current folder' button to upload your index.html file to the /home/ubuntu directory.

3. **Move the HTML file to the /var/www/html directory and adjust the permission
   ```bash
     sudo mv /home/ubuntu/index.html /var/www/html/index.html
     sudo sudo chown www-data:www-data /var/www/html/index.html
     sudo chmod 644 /var/www/html/index.html


### Access the sign-in page

  - Open your web brower.
  - Navigate to your ip address of your EC2 instance
  - You should see your profile page displayed.

### Conclusion
 - By following these steps, you have successfully deployed a simple HTML profile page on an AWS
   EC2 instance using Apache/ all managed through mobaxterm.This guide covers the initial setup
   to get your webpage online


