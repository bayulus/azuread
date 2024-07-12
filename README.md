# Hands-On Lab: Implementing Active Directory and Automating User Creation With Powershell

<p>In this project, I set up an Active Directory environment and automated user creation using PowerShell. This lab provided a comprehensive, hands-on experience with Active Directory. I covered the installation of Active Directory Domain Services, the creation and configuration of Organizational Units (OUs) and Group Policies, and the automation of user account creation using PowerShell scripts. By the end of this lab, I had a fully functional Active Directory environment and a set of PowerShell scripts to streamline user management tasks.
</p>

💻 **Languages and Tools Used For This Project:** 🛠️

![Static Badge](https://img.shields.io/badge/WINDOWS%20SERVER-blue?style=flat-square)
![Static Badge](https://img.shields.io/badge/WINDOWS%20POWERSHELL-blue?style=flat-square)
![Static Badge](https://img.shields.io/badge/WINDOWS%2010-blue?style=flat-square)
![Static Badge](https://img.shields.io/badge/VIRTUAL%20BOX-blue?style=flat-square)

<h2>Here's A High-Level Outline of The Steps I Took For This Project 🧱</h2>

  - **Step 1:** I began by setting up a Windows Server virtual machine, which would serve as the **_domain controller_** housing Active Directory. Then I configured the virtual machine with two network adapters. One adapter connected to the outside internet, while the other was set up for the private network within VirtualBox, using the private IP range 192.168.0.1.
  - **Step 2:** Next, I installed Active Directory on the domain controller and created a domain(orgdomain.com). I ensured that routing was configured correctly so that clients on the private network could access the internet through the domain controller.
  - **Step 3:** To streamline IP address management for the Windows 10 client machines, I set up DHCP on the domain controller. This allowed the client machines to automatically obtain IP addresses from the internal network (192.168.0.X)
  - **Step 4:** After setting up the DHCP, I wrote and executed a PowerShell script to automate the creation of a thousand users in Active Directory.
  - **Step 4:** 

I configured the virtual machine with two network adapters. One adapter connected to the outside internet, while the other was set up for the private network within VirtualBox, using the private IP range 192.168.0.1.

Installing and Configuring Active Directory:
Next, I installed Active Directory on the domain controller and created our domain. I ensured that routing was configured correctly so that clients on the private network could access the internet through the domain controller.

Setting Up DHCP:
To streamline IP address management for our Windows 10 client machines, I set up DHCP on the domain controller. This allowed the client machines to automatically obtain IP addresses from the internal network (192.168.0.X).

Automating User Creation with PowerShell:
Before proceeding to create our client virtual machine, I wrote and executed a PowerShell script on the domain controller. This script automated the creation of a thousand users in Active Directory, saving time and ensuring consistency in user management tasks.
