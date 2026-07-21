# *Static_WebSite_Hosting* 
# *Project Introduction* 
### This project demonstrates the deployment of a static website on an Amazon EC2 instance using the Nginx web server. A static website consists of fixed web pages built with HTML, CSS, and JavaScript, which are delivered directly to users without any server-side processing or database connectivity.

### The application follows a single-server deployment model, where both the website content and the Nginx web server reside on the same EC2 instance. The website files are stored in the default Nginx web root directory (/usr/share/nginx/html), enabling Nginx to efficiently serve the content through the instance's public IP address.
# 1. Architecture Overview
![Architecture Overview](./images/static-website-hosting-aws-architecture%20(1).png)
# 2. Instance Setup
# 2.1 Launch Instance
![](./images/Screenshot%202026-05-21%20205331.png)
# 2.2 Names & OS 
### Name : `Static-Web-Hosting`
### OS : `Amazon Linux` 
![](./images/Screenshot%202026-05-21%20205417.png)
# 2.3 AMI & Instance Type
### AMI : `Default`
### Architecture : `Default`
### Instance Type : `t3.micro` (2CPU & 1GB Memory)
![](./images/Screenshot%202026-05-21%20205648.png)
# 2.4 Key & Network
### Key : `MY-north-virginia-key` (Exiting One)
### Security Group :  `Launch-Wizard-1` (Exiting One)
![](./images/Screenshot%202026-05-21%20205726.png)
# 2.5 Start Instance
![](./images/Screenshot%202026-05-21%20205924.png)
# 2.6 Connect 
![](./images/Screenshot%202026-05-21%20210225.png)
# 2.7 Copy SSH Client Link
![](./images/Screenshot%202026-05-21%20210256.png)
#  3. Installing Packages
### 3.1 Open GitBash Where Your Private Is Stored(.pem)
![](./images/Screenshot%202026-05-21%20211819.png)
# 3.2 Connect Instance With SSH Key
### `ssh -i MY-north-virginia-key.pem` ec2-user@ec2-54-175-213-69.compute-1.amazonaws.com 
# 3.3 Update Packages
### `sudo yum updat`
# 3.4 Install Nginx
### `sudo yum install nginx -y`
# 3.5 Start Nginx
###  `sudo systemctl start nginx`
# 3.6 Enable Nginx
### `sudo systemctl enable nginx` 
# 3.7 Check Status Nginx 
### `sudo systemctl status nginx`
![](./images/Screenshot%202026-05-21%20212408.png) 
# 4. Running Static App
### 4.1 Go To Nginx Default Directory 
### `cd /usr/share/nginx/html`
# 4.2 Remove Existing Files
### ` sudo rm -rf *.html *.png icons`
# 4.3 Create Index, Style & Script FIles 
`sudo vim index.html`
`sudo vim style.css`
`sudo vim script.js`

![](./images/Screenshot%202026-05-21%20213959.png)
![](./images/Screenshot%202026-05-21%20214111.png)
![](./images/Screenshot%202026-05-21%20214303.png)
# 4.4 Restart Nginx
### `sudo systemctl restart nginx`
# 5. Access On Browser
### 5.1 Hit It On Browser And Put File Name
`13.52.77.167/netflix/`
![](./images/Screenshot%202026-05-22%20215225.png)
### 6.This project demonstrates how to host a static website on an Amazon EC2 instance using the Nginx web server. The website is built with HTML, CSS, and JavaScript, and is deployed by storing the static files in the default Nginx web root directory. Nginx serves the website directly to users through the EC2 instance's public IP address, providing fast and reliable access without requiring a backend application or database. This project highlights the fundamentals of web server configuration, Linux administration, and static website deployment on AWS.