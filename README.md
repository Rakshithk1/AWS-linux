# AWS-linux
"Hands-on AWS and Linux projects for cloud deployment, server management, and automation."

This repository contains AWS and Linux-related setup files, including EC2 instance deployment and website hosting.

**OPEN FREE TRIAL OF AWS**
        Search for EC2
          Click on Launch instance
          choose the OS you want-- I have selected AWS
          Choose the free tier t2.micro
          select pem.key, you can also create one
          Edit the network settings and enable SSH port 22 and HTTP port 80 for remote access and our website to load in server
          click on launch instance
Open mobaexterm or Putty-- click on new terminal---SSH
           Copy the private IP which will be in the new instance we have created
           paste that in the remote server section
           And enter Ec2-user in the user details
           click on advance and select the pem.key we have created in EC2
           Now you will be able to connect to the server
           Enter Sudo -i                               #here you will be able to access the root Ec2
           now you have to install httpd for the website to load and to get the html path
           Enter the cmd yum install httpd -y
           once done, cd/var/www/html
           echo "Welcome to EC2 server" >>index.html   #this saves the content to be displayed.
           now you have to start the httpd
           service sshd start
           service sshd status
           If you dont see the website, use service sshd restart
           You can search the EC2 ip in the browser and your website would be loading. 
 **Step 2 using the normal user of the ec2**
         you can create an user using useradd username
         passwd username
         you wont able to install the httpd since this new user do not have the permission. 
         So you will have to add him to the root main grouo
         usermod -aG wheel username
         once the user is added, he can use the same above steps and run the website. 

     **Once the website is working, you can stop the EC2 instance or terminate it so that it wont charge you**    
