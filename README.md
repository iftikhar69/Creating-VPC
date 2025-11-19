# 🌐 AWS VPC – Beginner-Friendly Study Notes (2025)

This repository contains my personal study notes for understanding and building an **AWS Virtual Private Cloud (VPC)** from scratch.  
It is written in simple, human-friendly language so anyone visiting this repo can learn AWS networking clearly and quickly.

🔹 I maintain a separate repository for the VPC Terraform modules.  
🔹 **This repo is only for learning and architecture notes — no Terraform here.**

---

## 📘 What This Repo Covers

These are the exact topics I studied and summarized:

- What a VPC is and why AWS uses it
- How VPC fits inside AWS global cloud infrastructure
- Public and private subnet design
- Internet Gateway (IGW)
- NAT Gateway for private subnets
- Route tables and routing logic
- Launching EC2 instances inside VPC
- SSH access to public EC2
- Cleaning up AWS resources safely

---

## 🎥 Tutorial Timeline (My Notes)

📺 **Full Tutorial Video:** https://www.youtube.com/watch?v=pfcHN5sPpCI  

- **00:00** – Introduction to AWS VPC  
- **00:41** – What is AWS VPC & Why Use It?  
- **03:28** – VPC inside the overall AWS Public Cloud  
- **07:41** – How public & private subnets access the Internet  
- **09:55** – Creating your AWS VPC  
- **11:36** – Setting up Public & Private Subnets  
- **14:46** – Configuring Internet Gateway (IGW)  
- **16:07** – Creating & Associating Route Tables  
- **21:07** – Setting up NAT Gateway for Private Subnet  
- **24:56** – Launching an EC2 Instance  
- **29:58** – SSH into the EC2 Server  
- **33:00** – Deleting AWS Resources  


---

## 🖼️ AWS VPC Architecture Diagram (Blueprint Style)
<img width="2342" height="1666" alt="image" src="https://github.com/user-attachments/assets/77434b32-62aa-45cd-a37f-a057c2fa6ff3" />

---


## 🧠 Simple Explanation of AWS VPC Architecture

### **1. VPC (Virtual Private Cloud)**
A VPC is your own private network inside AWS.  
You control the IP ranges, subnets, routing, and security.

---

### **2. Subnets**
Subnets divide the VPC network into smaller parts.

| Subnet Type | Purpose | Internet Access |
|-------------|---------|-----------------|
| **Public Subnet** | Web servers, Bastion hosts | Yes (via IGW) |
| **Private Subnet** | Databases, internal apps | Yes (via NAT Gateway) |

---

### **3. Internet Gateway (IGW)**
The IGW allows public subnets to access the internet.

- It is attached to the VPC  
- The route table sends `0.0.0.0/0` traffic to the IGW  

---

### **4. Route Tables**
Route tables tell AWS where network traffic should go.

Examples:

| Destination | Target | Meaning |
|-------------|--------|---------|
| `0.0.0.0/0` | IGW | Public subnet internet access |
| `0.0.0.0/0` | NAT Gateway | Private subnet outgoing access |

---

### **5. NAT Gateway**
A NAT Gateway lets private instances access the internet for:

- OS updates  
- Package installation  
- API communication  

But it does **not** allow inbound internet traffic to reach them.

---

### **6. EC2 Instances in the VPC**
Typical VPC design includes:

- Public EC2 instance (SSH, web server)
- Private EC2 instance (backend, internal services)

---

### **7. Cleaning Up AWS Resources**
To avoid charges :

- Delete NAT Gateway  
- Release Elastic IP  
- Delete IGW  
- Delete custom route tables  
- Delete subnets  
- Delete the VPC  

---

## 🎯 Purpose of This Repository

This repo is made for:

- Beginners learning AWS networking  
- Students preparing for AWS certification  
- Developers understanding VPC architecture  
- Anyone wanting a simple explanation of VPC concepts  

No complex text.  
No overwhelming diagrams.  
Just simple, visual, clean AWS knowledge.

---

## 📬 Contributions

Feel free to open issues or suggest improvements anytime.
