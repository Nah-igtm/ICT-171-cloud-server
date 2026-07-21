

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

Start by creating a virtual machine , you are free to choose any but here w will be using microsoft azure. first lets start ny logging into azure account and then searching virtual machine and then start to create a vm.


**This section details the step-by-step process of provisioning a cloud Virtual Machine (VM) using Microsoft Azure under the **Infrastructure as a Service (IaaS)** service model.Start by creating a virtual machine , you are free to choose any cloud service provider but here we will be using microsoft azure. 

---

## 1. Navigating to Virtual Machine Creation
1. Log into the [Microsoft Azure Portal](https://portal.azure.com/).
2. In the top search bar, search for **Virtual machines** and select it under Services.
3. Click **Create** $\rightarrow$ **virtual machine**.

---

## 2. Configuring VM Basics & Instance Details


 * **Subscription** : Choose Azure for Students 
 * **Resource Group** :Create new $\rightarrow$ Name it appropriately (e.g., `rg-portfolio-project`) 
 * **Virtual Machine Name** :Give a relevant identifier (e.g., `vm-ict171-portfolio`)
 * **Region** :Select a recommended nearby region 
 * **Availability Zone** :Leave as Default 
 * **VM Architecture**  :Leave as Default (`x64`) 
 * **Image**  :**Ubuntu Server 24.04 LTS - x64 Gen2** 
 * **Size**  :Click see all sizes and choose depending on the budget relative to the computational power needed for you choose, b-series is highly recommended **B1s** (1 vCPU, 1 GiB RAM) or **B2s** (newer version of B-Series), for a static website portfolio you can choose from the b1 series, which is 1cpu and 1 gb of ram.

> 💡 *Note: If B-Series sizes are unavailable, select "See all sizes" or switch the target region.*

---

## 3. Authentication & Inbound Network Security Rules

### Authentication Setup
* **Authentication Type:** Select **SSH public key**.
* **Key Pair Name:** Generate a new key pair, give a username and a name for the key.By default, Azure uses key files rather than a username and password to verify your identity when logging into your virtual machine. If you lose this file it is unlikely you will be able to mange your virtual machine so it is important to keep it safe.
* **Notice:** *Download and save your `.pem` key file in a secure local location.*

### Inbound Firewall Rules (Network Security Group)
Configure the Network Security Group (NSG) to allow standard administrative and web traffic:
* **Click "Select inbound ports"
* **There is an existing SSH permission that is needed to manage your remote server, that is fine.
* **HTTP (Port 80):** Allows standard web traffic and Let's Encrypt domain verification.
* **HTTPS (Port 443):** Allows encrypted, secure web traffic.

---

## 4. Disks, Networking, & Resource Deployment

1. **Disks:** Maintain the default **30 GB OS disk** allocation.
2. **Networking:** Keep default subnet and public IP settings.
3. **Management, Monitoring, & Tags:** Skip optional tagging configurations.
4. **Review + Create:** Validate settings and click **Create+create**.
5. **Download Private Key:** Promptly save the generated `.pem` file to your local computer when prompted.

---

## 5. Connecting via SSH Terminal

Once deployment is complete, navigate to your Virtual Machine resource page to retrieve connection credentials.

1. Open the **Overview** blade of your VM and locate the **Public IP address**.
2. Click **Connect** $\rightarrow$ **SSH client**.
3. Open Command Prompt (Windows) or Terminal (macOS/Linux) on your local computer.
4. Navigate to the folder containing your downloaded `.pem` key file using cd and execute the SSH command:

```bash
ssh -i "yourkeyname.pem" your_username@your_azure_vm_ip_address
```
