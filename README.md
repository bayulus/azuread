# Hands-On Lab: Implementing Active Directory and Automating User Creation With Powershell

<img src="https://github.com/bayulus/azuread/blob/main/img/azureadlab.png">

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
  - **Step 5:** With Active Directory set up and users created, I proceeded to install Windows 10 as a client machine. I configured it to use the internal network, where it automatically obtained its IP address from the domain controller. This seamless integration allowed the Windows 10 client to authenticate using one of the users created in AD, demonstrating the successful implementation of our Active Directory environment.

# Installing and Setting up The Windows Server 
<p>I began by setting up our first Windows Server virtual machine to serve as the domain controller. This machine is essential because it will host Active Directory (AD), which is crucial for centralizing user and computer management within our network. I set up the network configuration to use Network Address Translation (NAT) to allow the virtual machine to access the external internet for updates and other resources.</p>

<img src="https://github.com/bayulus/azuread/blob/main/img/1a.PNG?raw=true" >

<p>The second adapter was configured to use an internal network within VirtualBox, set to the IP range 192.168.0.1. This internal network allows secure communication between the domain controller and client machines in our virtual environment.</p>

<img src="https://github.com/bayulus/azuread/blob/main/img/1b.PNG?raw=true" >

<p>I named the NAT adapter x_Internet and the internal network adapter i_Internal, configuring the internal network to use the IP range 192.168.0.1 </p>

<img src="https://github.com/bayulus/azuread/blob/main/img/4.PNG?raw=true" >

----

<img src="https://github.com/bayulus/azuread/blob/main/img/2.PNG?raw=true" >

# Installing and Configuring Active Directory

<p>I configured the local server and installed Active Directory Domain Services (AD DS). Installing AD DS is essential for creating and managing a centralized domain, which allows for efficient administration of users, computers, and other network resources.</p>

<img src="https://github.com/bayulus/azuread/blob/main/img/3.PNG?raw=true" >

----

<img src="https://github.com/bayulus/azuread/blob/main/img/5.PNG?raw=true" >

<p>After installing Active Directory Domain Services (AD DS), the next step was to manually promote the server to a domain controller. This process involves configuring the server to manage and authenticate domain resources. I set the domain name to orgdomain.com, establishing it as the primary domain for the network</p>

<img src="https://github.com/bayulus/azuread/blob/main/img/6.PNG?raw=true" >

----

<img src="https://github.com/bayulus/azuread/blob/main/img/7.PNG?raw=true" >

<p>After promoting the server to a domain controller, the system required a restart to complete the configuration. Once the server was back online, I was able to log in using the same credentials that were used to create the server. However, now these credentials granted me administrative access with domain controller privileges.</p>

<img src="https://github.com/bayulus/azuread/blob/main/img/8.PNG?raw=true" >

<p>After the restart, I accessed Active Directory Users and Computers and created a new user in the Admin folder. Using this new user account, I can now log in with administrative privileges.</p>

<img src="https://github.com/bayulus/azuread/blob/main/img/9.PNG?raw=true" >

----

<img src="https://github.com/bayulus/azuread/blob/main/img/10.PNG?raw=true" >












