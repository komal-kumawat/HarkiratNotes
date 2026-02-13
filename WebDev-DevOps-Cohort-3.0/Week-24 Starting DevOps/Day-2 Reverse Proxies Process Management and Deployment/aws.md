## ☁️ What is AWS?

**Amazon Web Services (AWS)** is a cloud computing platform provided by **Amazon**.

It allows companies and developers to **rent computing resources over the internet** instead of buying physical servers.

Instead of:

* Buying servers
* Setting up data centers
* Managing hardware

You can use AWS services online and **pay only for what you use**.

---

# 🌍 How AWS Works (Simple Explanation)

Imagine AWS as a **huge online data center**.

You can:

* Rent a computer (server)
* Store files
* Run applications
* Host websites
* Build AI models
* Create databases
* Set up networking

All without buying physical machines.

---

# 🏗️ AWS Global Infrastructure

![Image](https://res.cloudinary.com/hy4kyit2a/f_auto%2Cfl_lossy%2Cq_70/learn/modules/aws-cloud-technical-professionals/explore-the-aws-global-infrastructure-technical-professionals/images/d88d2fecf52142786da539be437e50df_d-11-f-53-af-b-76-f-482-d-8492-73-be-2-a-630-f-1-b.png)

![Image](https://docs.aws.amazon.com/images/AWSEC2/latest/UserGuide/images/region-with-wavelength-zones.png)

![Image](https://www.techtarget.com/rms/onlineimages/aws_availability_zones_vs_regions-f_mobile.png)

![Image](https://www.netapp.com/media/aws-regions-1_tcm19-128029.png)

AWS has:

### 1️⃣ Regions

Physical locations around the world (e.g., Mumbai, US-East, Europe).

Example:

* Asia Pacific (Mumbai)
* US-East (Virginia)

### 2️⃣ Availability Zones (AZs)

Each region has multiple data centers (AZs).
This ensures **high availability and fault tolerance**.

---

# 🧱 Core AWS Services (Very Important for Interviews)

AWS has 200+ services. Let’s focus on major categories:

---

# 1️⃣ Compute Services (Running Applications)

These services provide virtual machines and computing power.

### 🔹 EC2 (Elastic Compute Cloud)

Amazon EC2

* Virtual server in the cloud
* You choose:

  * OS (Linux/Windows)
  * RAM
  * CPU
  * Storage

👉 Used for hosting backend, APIs, applications.

---

### 🔹 Lambda (Serverless)

AWS Lambda

* Run code without managing servers
* Event-driven
* Pay per execution

👉 Used in microservices & automation.

---

### 🔹 Elastic Beanstalk

AWS Elastic Beanstalk

* Deploy web apps easily
* Automatically handles scaling

---

# 2️⃣ Storage Services

### 🔹 S3 (Simple Storage Service)

Amazon S3

* Store files (images, videos, backups)
* Highly durable (99.999999999%)

👉 Used for:

* Static website hosting
* Image storage
* Backups

---

### 🔹 EBS (Elastic Block Store)

Amazon EBS

* Storage attached to EC2
* Like a hard disk

---

### 🔹 Glacier

Amazon S3 Glacier

* Very cheap storage
* Used for long-term backups

---

# 3️⃣ Database Services

### 🔹 RDS (Relational Database Service)

Amazon RDS

Supports:

* MySQL
* PostgreSQL
* Oracle
* SQL Server

👉 Fully managed database.

---

### 🔹 DynamoDB

Amazon DynamoDB

* NoSQL database
* Extremely fast
* Serverless

---

# 4️⃣ Networking Services

### 🔹 VPC (Virtual Private Cloud)

Amazon VPC

* Private network in AWS
* Control IP ranges
* Security groups
* Subnets

---

### 🔹 Route 53

Amazon Route 53

* Domain management
* DNS service

---

### 🔹 CloudFront

Amazon CloudFront

* CDN
* Delivers content faster globally

---

# 5️⃣ Security Services

### 🔹 IAM (Identity and Access Management)

AWS Identity and Access Management

* Manage users
* Roles
* Permissions

---

### 🔹 KMS

AWS Key Management Service

* Manage encryption keys

---

# 6️⃣ Monitoring & DevOps

### 🔹 CloudWatch

Amazon CloudWatch

* Monitor servers
* Track logs
* Set alarms

---

### 🔹 CodePipeline

AWS CodePipeline

* CI/CD automation

---

# 💰 AWS Pricing Model

AWS follows:

* Pay-as-you-go
* No upfront cost
* Billing per second/hour
* Free tier available (12 months)

---

# 🧠 Important Cloud Concepts

### 🔹 Scalability

Automatically increase/decrease servers.

### 🔹 Elasticity

Resources adjust automatically with demand.

### 🔹 High Availability

Multiple AZs prevent downtime.

### 🔹 Fault Tolerance

System continues working even if one part fails.

---

# 🏢 Real-World Use Case Example

Suppose you build a MERN app:

* Frontend → S3
* Backend → EC2
* Database → RDS
* Images → S3
* Domain → Route 53
* CDN → CloudFront
* Monitoring → CloudWatch

This is a typical production architecture.

---

# 🏆 Why Companies Use AWS

* No hardware cost
* Global reach
* Security compliance
* Auto-scaling
* Serverless options
* AI/ML tools available

---

# 🚀 AWS vs Traditional Hosting

| Traditional       | AWS              |
| ----------------- | ---------------- |
| Buy servers       | Rent servers     |
| Fixed capacity    | Auto-scale       |
| High upfront cost | Pay-as-you-go    |
| Manual setup      | Managed services |

---

# 📌 Is AWS Important for You (As a CSE Student)?

Yes ✅ Especially for:

* SDE roles
* DevOps
* Backend development
* System design interviews

Even Google SDE interviews expect:

* Cloud basics
* Scalability concepts
* Distributed systems knowledge

---
