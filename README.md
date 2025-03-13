### Apache 2 Web Server Setup on Ubuntu Linux :
this project provides a detailed guide for installing, configuring, and managing the Apache 2 HTTP Server on Ubuntu 22.04 LTS. 
Apache is a widely adopted open-source web server known for its reliability and flexibility. This project focuses on setting up a basic web server to host static websites, 
configuring virtual hosts for multiple sites, and implementing log monitoring for maintenance. Aimed at beginner-to-intermediate users with basic Linux knowledge, 
this documentation offers a practical, streamlined approach to apache2  server administration .

## Problem Statement
Deploying a web server poses several challenges for newcomers:
Installation Barriers: Understanding package management and service control on Linux can be intimidating for beginners.
Multi-Site Hosting: Configuring a server to host multiple websites efficiently requires knowledge of virtual hosts.
Maintenance Oversight: Without log monitoring, server issues like errors or high traffic may go unnoticed, affecting performance.
This project addresses these issues by delivering a clear, step-by-step solution to install and manage an Apache 2 server on Ubuntu, 
focusing on static content hosting and basic administration

## Methodology
The methodology is divided into three phases: installation, configuration, and management. Each step includes commands, file snippets, and explanations tailored for clarity.
- Installation
```
sudo apt update && sudo apt upgrade -y
```
- Install Apache 2
  ```
  sudo apt install apache2 -y
  sudo systemctl start apache2
  sudo systemctl enable apache2
  sudo systemctl status apache2
  ```
  ![Apache2 Running ](https://raw.githubusercontent.com/rukevweubio/Basic-Apache-2-Web-Server-Configuration-on-Ubuntu-Linux/main/Screenshot%20(475).png)
  ## Create Website Directories
  ```
 sudo mkdir -p /var/www/site1.com/public_html
sudo mkdir -p /var/www/site2.com/public_html
sudo chown -R $USER:$USER /var/www/site1.com/public_html /var/www/site2.com/public_html
sudo chmod -R 755 /var/www/site1.com /var/www/site2.com
```
## Add Sample Content:
``` nano /var/www/site1.com/public_html/index.html
```
## Management
``` sudo apt install logwatch -y
  sudo logwatch --service apache --range Today --detail Med --format text
  ```
## test website

