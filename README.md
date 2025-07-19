# ☁️ Cloud Deployment: PHP Web Application on AWS

> 🚨 **Note:** This project demonstrates my ability to deploy a secure, cloud-native PHP application on AWS using EC2, RDS, VPC, and related services.  
> The application used is open-source and credited below. My contribution lies in designing the infrastructure and successfully deploying the system end-to-end.

---

## 📌 Project Overview

This deployment simulates a real-world production setup of a PHP-based **Student Management System** hosted on AWS, with an emphasis on secure architecture, hands-on networking, and CLI-driven configuration.

### 🔧 Stack Highlights:
- **Amazon EC2** – For hosting the PHP web server
- **Amazon RDS** – For storing student records in a MySQL DB
- **Custom VPC** – With public/private subnets, route tables, and internet gateway
- **Manual SQL Import** – From EC2 to RDS via MySQL CLI
- **End-to-end Testing** – Browser access, DB connection validation, and data verification

---

## 🧱 Architecture Diagram

![Architecture diagram](screenshots/architecture.png)

### 🗺️ Infrastructure Layout:
- Public subnet → EC2 instance (Web Server)
- Private subnet → RDS instance (MySQL)
- Separate private subnet → Standby/AZ2
- Internet Gateway + NAT routing
- Custom security groups for HTTP, SSH, and DB access

---

## 🛠️ Tools & Services Used

| Category       | Tools/Services                           |
|----------------|------------------------------------------|
| Compute        | Amazon EC2 (Amazon Linux 2023)           |
| Database       | Amazon RDS (MySQL 8.0)                   |
| Networking     | VPC, Subnets, Route Tables, IGW, SGs     |
| Access Control | IAM, Key Pairs                           |
| Dev Tools      | Git, CLI, Netcat (`nc`), MySQL CLI       |

---

## 🚀 Deployment Steps (Summary)

1. **VPC & Subnet Setup**
   - CIDR Block: `10.0.0.0/24`
   - 3 Subnets (1 public, 2 private across AZs)

2. **Routing & Internet Access**
   - Attached Internet Gateway to public subnet
   - Created custom route tables for public/private traffic

3. **EC2 Instance Configuration**
   - Installed Apache, PHP, and MySQL client
   - Cloned project via Git and configured `config.php`

4. **RDS Setup**
   - Private subnet placement, custom SG
   - Whitelisted EC2 in DB SG for secure access

5. **App + Database Integration**
   - Imported `.sql` into RDS via MySQL CLI
   - Verified connection and data flow via UI

---

## 📸 Screenshots

### 🌐 Web App Access & Data Entry

**Browser Access and Form Submissions:**  
![Step 1](./screenshots/Screenshot%20%28587%29.png)  
![Step 2](./screenshots/Screenshot%20%28588%29.png)  
![Step 3](./screenshots/Screenshot%20%28589%29.png)  
![Step 4](./screenshots/Screenshot%20%28590%29.png)  
![Step 5](./screenshots/Screenshot%20%28591%29.png)  
![Step 6](./screenshots/Screenshot%20%28592%29.png)

These screenshots demonstrate public access to the app and successful interaction with the backend DB through user inputs.

---

### 🧪 Remote DB Validation

**MySQL CLI Check for Data:**  
![Step 1](./screenshots/Screenshot%20%28599%29.png)  
![Step 2](./screenshots/Screenshot%20%28600%29.png)

Data entered through the frontend is visible inside the MySQL RDS instance, confirming proper integration between the app and the database.

---


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

## 🙏 Credits

This project uses the open-source **Student Management System** from [PHP Gurukul](https://phpgurukul.com/student-management-system-using-php-and-mysql/).  
All rights and content belong to the respective authors. I used the code solely for deployment and infrastructure demonstration purposes.

---

## 🧹 Cleanup & Cost Note

After successful deployment and testing, **all AWS resources were deleted** to avoid incurring further cloud charges.  
As this was a **learning-focused, non-commercial project**, every component was manually cleaned up via the AWS Console.

---

## ✅ Outcome

- Designed and deployed a secure 3-tier architecture
- Connected PHP app to MySQL RDS via private subnets
- Validated app functionality and DB communication
- Practiced real-world deployment, networking, and troubleshooting skills


---

If you’d like to learn more or want help setting up something similar — reach out!

