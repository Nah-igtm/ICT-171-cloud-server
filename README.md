# ICT171 Cloud Server Project: Personal Portfolio Website

* **Student Name:** Muhammad Nahshal  
* **Student ID:** 35512854                                                                              
* **Live Site IP:** `20.248.209.74`  
* **Live Domain:** https://mn-cybr.online  
* **Video Explainer:** [Your Video Link Here]  

---

## Project Overview
This repository contains the comprehensive technical documentation for deploying and managing my live Personal Portfolio Website. Built as part of the ICT171 Cloud Server Project, this environment leverages an **Infrastructure as a Service (IaaS)** framework rather than a pre-packaged SaaS solution to maximize administrative control and system customization. 

The site is hosted on a right-sized **Microsoft Azure B1s Virtual Machine** running **Ubuntu 24.04 LTS**, utilizing **Nginx** as the web server, and secured with manually configured **SSL/TLS certificates** via Let's Encrypt. This repository serves as a step-by-step replication guide to completely rebuild this server environment from scratch[cite: 1].


##Development Timeline
The project was developed iteratively over 4 weeks:

Week 1: Initial cloud infrastructure setup, Azure B1s virtual machine provisioned, and Network Security Group (NSG) firewall rules configured.

Week 2: Installed Nginx web server, customized local HTML/CSS portfolio assets, and mapped root server directory paths.

Week 3: Acquired mn-cybr.online domain via Porkbun, configured DNS A-records, and deployed Let's Encrypt SSL/TLS certificates using Certbot.

Week 4: Engineered custom Bash backup script (backup_portfolio.sh), scheduled daily automated execution via cron, and finalized documentation.

##Features
Cloud Infrastructure: Deployed on an Azure Ubuntu 24.04 LTS IaaS Virtual Machine.

Secure Web Server: Configured Nginx web server delivering high performance and low resource overhead.

Encrypted Traffic (HTTPS): Full SSL/TLS implementation using Let's Encrypt and Certbot with enforced HTTP-to-HTTPS redirection.

Custom Domain Routing: Porkbun DNS resolution mapped directly to the static public IP (20.248.209.74).

Automated Maintenance: Custom Bash backup script (backup_portfolio.sh) running daily at 2:00 AM via system cron with dynamic logging and a 7-day retention cleanup.

##Tools Used
Microsoft Azure VM (Ubuntu): Cloud compute provider (IaaS).

Nginx: Web server software.

Certbot (Let's Encrypt): Automated SSL/TLS certificate management.

Porkbun: Domain registrar and DNS management.

Bash & Cron: Shell scripting and automated task scheduling.
