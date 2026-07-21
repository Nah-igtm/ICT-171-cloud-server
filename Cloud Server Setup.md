

## Cloud Server Setup

* **Student Name:** Muhammad Nahshal  
* **Student ID:** 35512854                                                                              
* **Live Site IP:** `20.248.209.74`  
* **Live Domain:** https://mn-cybr.online  
* **Video Explainer:** [Your Video Link Here]  

---

## Project Overview
This repository contains the comprehensive technical documentation for deploying and managing my live Personal Portfolio Website. Built as part of the ICT171 Cloud Server Project, this environment leverages an **Infrastructure as a Service (IaaS)** framework rather than a pre-packaged SaaS solution to maximize administrative control and system customization. 

The site is hosted on a right-sized **Microsoft Azure B1s Virtual Machine** running **Ubuntu 24.04 LTS**, utilizing **Nginx** as the web server, and secured with manually configured **SSL/TLS certificates** via Let's Encrypt. This repository serves as a step-by-step replication guide to completely rebuild this server environment from scratch

## Infrastructure Details
Cloud Provider: Microsoft Azure (Infrastructure as a Service)

Virtual Machine: Standard B1s Instance

Operating System: Ubuntu 24.04 LTS

Public IP Address: 20.248.209.74

Server Size: 1vcpu and 1gb Ram (cheap and suufiecient for static portfolio website)

Domain registrar and DNS: Porkbun (mn-cybr.online)

Web Server: Nginx

Encryption: SSL/TLS Certificate via Let's Encrypt (Certbot)

Start by creating a virtual machine , you are free to choose any but here w will be using microsoft azure. first lets start ny logging into azure account and then searching virtual machine and then start to create a vm 

creating a vm in azure :-
after clicking on create vm follow the steps on azure 
now from the subscription part you can choose azur for student 
Resource group:- give a name and then give the vm name (give it anything related to project)
Region - Pick up one from the recommended region.
Availability zone - At the moment you can leave it as the default.
vm arvhitechure can be left as defualt 
Image - Pick "Ubuntu Server 24.04 LTS".
Size - This relates to the resource you got and the price you will be paid for the computational power for the VM. Try to pick a "B-Series" size, as it is the most budget friendly. If you cannot find it, try switch to another zone and region. click on see all sizes and big the most budgeyt frienldy relative to the computational power. for a static website portfolio you can choose from the b1 or b2 series, which has 1cpu and 1 gb of ram.
Authetication type: choose SSh key .generate a new key pair. By default, Azure uses key files rather than a username and password to verify your identity when logging into your virtual machine. If you lose this file it is unlikely you will be able to mange your virtual machine so it is important to keep it safe.
Configure Inbound port rules
There is an existing SSH permission that is needed to manage your remote server, that is fine.
Click "Select inbound ports" and select HTTP (80) and HTTPS (443) as the type. This allows web requests to be received by our server and HTTPS (443) Allows encrypted, secure web traffic so users can access your portfolio safely.
Configure disks - The default is to create a virtual machine with an 30GB OS disk. That's fine, leave it at the default.
networking - leave it at the default.
Add management, monitoring and tag configuration - There is no need to add those configuration at the moment. So continue to "Review + create".
Launch Instance - Click on "Create" and your server will start. After this you can use "Notifications" to monitor it's progress.

Now that your server is running in the cloud you need to click on your vm and it will display an overview there you will press connect button. Then click on SSH client and note the string provided.   
open cmd or macos terminal paste the provided string
ssh -i "yourkeyname.pem" your_username@your_azure_vm_ip_address
