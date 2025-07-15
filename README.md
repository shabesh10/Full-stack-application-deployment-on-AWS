# ☁️ Cloud Deployment: PHP Web Application on AWS

> 🚨 Note: This project showcases my ability to deploy and configure a cloud-native infrastructure on AWS.  
> The PHP application used is open-source and not authored by me. The focus here is on **infrastructure setup, server provisioning, and secure deployment**.

---

## 📌 Project Overview

This deployment simulates a real-world production setup of a PHP-based student management system on AWS using:

- Amazon EC2 (for web server)
- Amazon RDS (MySQL-compatible)
- Custom VPC with public and private subnets
- Security groups, route tables, and internet gateway
- Manual `.sql` import via CLI from EC2 to RDS

---

## 🧱 Architecture Diagram

📷 ![Architecture diagram](screenshots/architecture.png)
✅ Example layout:
- Public subnet (EC2 instance)
- Private subnet (RDS instance)
- Another private subnet (standby)
- IGW attached to public subnet
- Separate route tables
- SSH and HTTP configured via security group rules

---

## 🛠️ Tools & Services Used

- **AWS EC2** – Amazon Linux 2023 (Apache, PHP)
- **AWS RDS** – MySQL 8.0 with private subnet group
- **AWS VPC** – Custom VPC with 3 subnets across 2+ AZs
- **AWS IAM** – Secure access via key pair
- **Git + CLI** – Used to clone and configure the PHP app
- **MySQL CLI** – Used to import `.sql` into RDS from EC2
- **Netcat (`nc`)** – Used to test DB port access from EC2

---

## 🌐 Deployment Steps (Summary)

1. ✅ **Create VPC and Subnets**
   - CIDR: `10.0.0.0/24`
   - Subnet A (public): `10.0.0.0/26`
   - Subnet B (private): `10.0.0.64/26` (RDS)
   - Subnet C (private standby): `10.0.0.128/26`

2. ✅ **Attach IGW and Route Tables**
   - Public RT → IGW route `0.0.0.0/0`
   - Associate subnets correctly

3. ✅ **Launch EC2 Instance**
   - Amazon Linux 2023
   - Installed Apache, PHP, MySQL client
   - Cloned project using Git
   - Edited `config.php` to point to RDS

4. ✅ **Create RDS MySQL DB**
   - Placed in private subnet
   - Security group allows access only from EC2
   - Connected using CLI + imported `.sql` file

5. ✅ **Test & Validate**
   - Accessed app via EC2 public IP
   - Verified DB interaction using MySQL CLI
   - Used `nc` and browser to validate ports and UI

---

## 📸 Screenshots

### 🔧 AWS Console Setup

**VPC Creation:**  
![VPC creation](./screenshots/Screenshot%20%28597%29.png)

**EC2 Instance Launch & Security Group Configuration:**  
![EC2 Launch](./screenshots/Screenshot%20%28593%29.png)  
![Security Group Config](./screenshots/Screenshot%20%28594%29.png)

**RDS Instance and Subnet Group:**  
![RDS setup](./screenshots/Screenshot%20%28595%29.png)


---


### 💻 EC2 Server Configuration

**Apache + PHP Installation to Web App Access:**  
![Step 1](./screenshots/Screenshot%20%28569%29.png)  
![Step 2](./screenshots/Screenshot%20%28570%29.png)  
![Step 3](./screenshots/Screenshot%20%28571%29.png)  
![Step 4](./screenshots/Screenshot%20%28572%29.png)  
![Step 5](./screenshots/Screenshot%20%28573%29.png)  
![Step 6](./screenshots/Screenshot%20%28574%29.png)  
![Step 7](./screenshots/Screenshot%20%28575%29.png)  
![Step 8](./screenshots/Screenshot%20%28576%29.png)  
![Step 9](./screenshots/Screenshot%20%28577%29.png)  
![Step 10](./screenshots/Screenshot%20%28578%29.png)  
![Step 11](./screenshots/Screenshot%20%28579%29.png)  
![Step 12](./screenshots/Screenshot%20%28580%29.png)  
![Step 13](./screenshots/Screenshot%20%28581%29.png)  
![Step 14](./screenshots/Screenshot%20%28582%29.png)  
![Step 15](./screenshots/Screenshot%20%28583%29.png)  
![Step 16](./screenshots/Screenshot%20%28584%29.png)


---


**Accessing Web App via Internet & Entering Data:**  
![Step 1](./screenshots/Screenshot%20%28587%29.png)  
![Step 2](./screenshots/Screenshot%20%28588%29.png)  
![Step 3](./screenshots/Screenshot%20%28589%29.png)  
![Step 4](./screenshots/Screenshot%20%28590%29.png)  
![Step 5](./screenshots/Screenshot%20%28591%29.png)  
![Step 6](./screenshots/Screenshot%20%28592%29.png)
These screenshots demonstrate successful public access to the deployed PHP web application from a browser, as well as interaction with the database through form inputs and submissions.

**Remote DB Access & Data Verification in RDS:**  
![Step 1](./screenshots/Screenshot%20%28599%29.png)  
![Step 2](./screenshots/Screenshot%20%28600%29.png)
These screenshots confirm that the data entered through the web app is successfully stored in the RDS MySQL database, verified via remote access from the EC2 instance.


