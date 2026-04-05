# 🧪 AWS Networking Lab: Public & Private Subnet Architecture

## 🎯 Objective
Design and deploy a secure AWS network using a custom VPC with public and private subnets, enabling controlled internet access and internal communication between resources.

---

## 🛠️ Services Used
- ☁️ Amazon VPC  
- 🖥️ Amazon EC2  
- 🌐 Internet Gateway  
- 📡 Route Tables  
- 🔐 Security Groups  

---

## 🧱 Architecture Overview
- 1 VPC (10.0.0.0/16)
- 1 Public Subnet (10.0.1.0/24)
- 1 Private Subnet (10.0.2.0/24)
- Public EC2 (SSH access)
- Private EC2 (internal only)

---

## 🚀 Step-by-Step Implementation

---

## 🌐 Step 1: Create a VPC

📝 **What you're doing:**  
Creating a Virtual Private Cloud to logically isolate an AWS network.

💡 **Why this matters:**  
The VPC is the foundation of the cloud environment. All resources must exist within it.

⚙️ **Steps:**
1. Navigate to VPC Dashboard  
2. Click **Create VPC**  
3. Set CIDR block to `10.0.0.0/16`  

✅ **Expected Result:**  
A new VPC is created and available for resource deployment.
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1775264485/Screenshot_2026-04-01_215111_itmjor.png" />

---

## 🌐 Step 2: Create Subnets (Public & Private)

📝 **What you're doing:**  
Creating separate network segments for public-facing and internal resources.

💡 **Why this matters:**  
Subnetting improves **security and organization** by isolating resources.

⚙️ **Steps:**
1. Go to **Subnets → Create subnet**  
2. Select the VPC  
3. Create:
   - Public Subnet → `10.0.1.0/24`  
   - Private Subnet → `10.0.2.0/24`  

✅ **Expected Result:**  
Two subnets successfully created within the VPC.
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1775264485/Screenshot_2026-04-01_215818_onsllt.png" />

---

## 🌐 Step 3: Attach an Internet Gateway

📝 **What you're doing:**  
Enabling internet access for resources in the public subnet.

💡 **Why this matters:**  
Without an Internet Gateway, the VPC cannot communicate with the internet.

⚙️ **Steps:**
1. Go to **Internet Gateways → Create**  
2. Attach it to the VPC  

✅ **Expected Result:**  
Your VPC now has internet connectivity capability.
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1775264481/Screenshot_2026-04-01_221038_zgqt66.png" />


---

## 📡 Step 4: Configure Route Tables

📝 **What you're doing:**  
Defining how traffic flows within the network.

💡 **Why this matters:**  
Route tables control whether resources can reach the internet or stay private.

⚙️ **Steps:**
1. Create a route table for the public subnet  
2. Add route:
   - Destination: `0.0.0.0/0`  
   - Target: Internet Gateway  
3. Associate this route table with the **public subnet**

✅ **Expected Result:**  
Public subnet can route traffic to the internet.
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1775264478/Screenshot_2026-04-01_221809_g8lwtf.png" />


---

## 🖥️ Step 5: Launch EC2 Instances

📝 **What you're doing:**  
Deploying virtual machines into the network.

💡 **Why this matters:**  
This simulates real-world workloads inside your cloud infrastructure.

⚙️ **Steps:**
1. Launch 2 EC2 instances:
   - Public EC2 → Public subnet  
   - Private EC2 → Private subnet  
2. Enable auto-assign public IP for public instance  

✅ **Expected Result:**  
Two running instances in separate subnets.
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1775264478/Screenshot_2026-04-01_222838_kt8293.png" />
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1775264478/Screenshot_2026-04-01_221851_syigwk.png" />
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1775264478/Screenshot_2026-04-01_222229_j0mt6e.png" />



---

## 🔐 Step 6: Configure Security Groups

📝 **What you're doing:**  
Controlling inbound and outbound traffic at the instance level.

💡 **Why this matters:**  
Security Groups act as a **virtual firewall**.

⚙️ **Steps:**
- Public EC2:
  - Allow SSH (port 22) from your IP  
- Private EC2:
  - Allow ICMP (ping) from **public EC2 security group**

✅ **Expected Result:**  
Secure and controlled communication between resources.
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1775394718/Screenshot_2026-04-05_091143_ghf49w.png" />


---

## 📡 Step 7: Connect to Public EC2 (Jump Host)

📝 **What you're doing:**  
Using the public EC2 instance as a **jump host (bastion)** to access internal resources, as well as being capable of testing the internal connection between the two instances. 

💡 **Why this matters:**  
The private EC2 does not have a public IP, so it **cannot be accessed directly from the internet**.  
The public EC2 acts as a secure entry point into the private network.

<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1775264477/Screenshot_2026-04-02_214408_iz56wk.png" />
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1775264477/Screenshot_2026-04-02_220306_jo2i6r.png" />



