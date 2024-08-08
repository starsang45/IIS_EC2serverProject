# Project Name: IIS_EC2serverProject
# Description
Launching EC2 Microsoft Windows Instance and deploy IIS (Internet Information Service)
# Purpose
Practicing launching AWS EC2 and deploying IIS converted Microsoft Windows webserver
# Installation and setup
Step 1: Launch an Window EC2 Instance
Log in to AWS Management Console:

Go to the AWS Management Console and log in with your credentials.
Navigate to EC2 Dashboard:

In the services menu, select EC2 to open the EC2 Dashboard.
Launch Instance:

Click on the Launch Instance button.
Choose an Amazon Machine Image (AMI):

Select a Windows Server AMI. You can find Windows Server options in the Quick Start tab.
Choose an Instance Type:

Select an instance type that meets your requirements (e.g., t2.micro for free tier eligibility).
Configure Instance Details:

Configure the instance details as needed. Ensure you have selected the correct VPC and subnet. Make sure to choose a subnet that has internet access (public subnet) if you plan to access the instance via the internet.
Add Storage:

Add storage as needed. The default settings are usually sufficient for a basic Windows Server setup.
Add Tags:

Add tags to help identify your instance (optional).
Configure Security Group:

Create a new security group or select an existing one. Ensure the security group allows RDP traffic:
Type: RDP
Protocol: TCP
Port Range: 3389
Source: Select My IP to allow your IP address or choose Anywhere for a broader access (less secure).
Review and Launch:

Review your settings and click on Launch.
Key Pair:

When prompted, select an existing key pair or create a new one. Download the key pair file (.pem) if you create a new one. This is essential for accessing your instance.
Launch Instance:

Click on Launch Instances

Step 2: Connect to the Windows Instance via RDP
Once the instance is running, you’ll need to connect to it using RDP (Remote Desktop Protocol).
Steps to Connect Using RDP:
1. In the EC2 dashboard, select the running instance.
2. Click on the Connect button at the top of the screen.
3. Under the RDP Client tab, click Download Remote Desktop File. This will download a .rdp file to your local machine.
4. Open the downloaded .rdp file. This will launch the Remote Desktop Connection application.
5. When prompted, enter the username (usually Administrator) and password provided by AWS. If you don't have the password, click on Get Password to retrieve it using your key pair.
6. Click OK to connect to the instance.
   
Step 3. Installing IIS and convert the instance into a web server

After logging into the Windows Server instance via RDP:
1. Open Server Manager from the start menu.
2. Click on Add roles and features to start the wizard.
3. Follow these steps:
-Installation Type: Select "Role-based or feature-based installation."
-Server Selection: Choose the local server (this is usually the default selection).
-Server Roles: Scroll down and check the box for Web Server (IIS).
-Features: You can leave the default features selected or add additional features based on your requirements.
-Confirmation: Review your selections and click Install.
5. Wait for the installation to complete. Once finished, your instance will have IIS installed, effectively converting it into a web server.

Step 4: Configuring IIS
1. Open Internet Information Services (IIS) Manager from the start menu.
2. Verify that the default website is running. You can do this by typing the public IP address of your EC2 instance into a web browser (e.g., http://<Public-IP>).
If needed, you can configure websites, add bindings, and set up SSL certificates.
 
Step 5: Test the Deployment
1. Open a web browser and enter the public IP address of your EC2 instance.
2. If everything is configured correctly, you should see the IIS welcome page
![Screenshot 2024-08-06 165502](https://github.com/user-attachments/assets/37958d7e-4a28-4f6d-b07a-2bf4030ce899)
![Screenshot 2024-08-06 164149](https://github.com/user-attachments/assets/6277eb58-52b3-4674-b613-204d8849d5f7)
# Usage
1. Web Application Hosting:
       Scenario: You have a web application built using ASP.NET or other technologies supported by IIS.
       Benefit: Hosting it on an AWS Windows Server instance with IIS provides a scalable, flexible, and cost-effective
       solution. You can easily manage traffic spikes, ensure high availability, and leverage AWS's global infrastructure.
3. Development and Testing Environment:
    Scenario: Your development team needs an environment that mirrors your production setup to test new features, perform
    integration testing, or run QA tests.
    Benefit: Using AWS, you can quickly spin up and tear down Windows Server instances with IIS, providing a consistent and
    isolated environment for your developers and testers.
5. Legacy Application Support:
    Scenario: You have legacy applications that require IIS for operation and cannot be easily migrated to other web servers or
    platforms.
    Benefit: Deploying these applications on AWS Windows Server instances with IIS ensures they continue to operate reliably,
    with the added benefits of cloud infrastructure such as backup, recovery, and monitoring.
7. Disaster Recovery:
    Scenario: You need a reliable disaster recovery solution for your web applications running on IIS.
    Benefit: By setting up IIS on AWS, you can replicate your web servers and have them ready to take over in case of an on-
    premises failure, ensuring business continuity and reducing downtime.
9. Scaling and Load Balancing:
    Scenario: Your web application needs to handle a large number of concurrent users and requires load balancing to distribute
    the traffic.

    Benefit: AWS allows you to deploy multiple Windows Server instances with IIS behind an Elastic Load Balancer (ELB),
    enabling automatic scaling based on demand and providing a seamless user experience.
11. Geographically Distributed Applications:
    Scenario: You need to serve users from different geographical regions with low latency.
    Benefit: AWS's global infrastructure lets you deploy IIS web servers in multiple regions, ensuring that users from various
    locations can access your application with minimal delay.
13. Secure Web Hosting:
    Scenario: Your application handles sensitive data and requires robust security measures.
    Benefit: AWS provides various security features such as Virtual Private Cloud (VPC), security groups, and encryption,
    which, when combined with IIS, can ensure a secure hosting environment for your web applications.
    
# License

This project is licensed under the Victor Sangmu Kim, making it freely available for anyone to use. 

