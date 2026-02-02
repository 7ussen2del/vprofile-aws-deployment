## ☁ AWS Services Used (IaaS Model)

- EC2 (Application Servers)
- EC2 (Database Server)
- EC2 (Cache & Messaging Services)
- Application Load Balancer
- Auto Scaling Group
- Security Groups
- Route 53
- S3 (for artifacts if applicable)

All components were installed and configured manually inside EC2 instances.

---

## 🔧 Prerequisites

- JDK 11
- Maven 3
- MySQL 8

---

## 🛠 Technologies

- Spring MVC
- Spring Security
- Spring Data JPA
- Maven
- JSP
- Apache Tomcat
- MySQL
- Memcached
- RabbitMQ
- ElasticSearch
- NGINX

---

## 🗄 Database Setup (MySQL on EC2 – IaaS)

MySQL 8 was manually installed on an EC2 instance.

Database dump file location:

/src/main/resources/db_backup.sql

### Step 1: Create Database

```bash
mysql -u root -p
CREATE DATABASE accounts;
EXIT;
```

### Step 2: Restore Database Dump

If running inside the database server:

```bash
mysql -u root -p accounts < src/main/resources/db_backup.sql
```

If restoring remotely:

```bash
mysql -h <EC2-PUBLIC-IP> -u root -p accounts < db_backup.sql
```

⚠ Ensure:
- Port 3306 is allowed in Security Group
- MySQL service is running
- Proper inbound rules are configured

---

## 🚀 Deployment Steps (High-Level)

1. Launch EC2 instances
2. Install required packages (Java, MySQL, Tomcat, etc.)
3. Configure NGINX as Load Balancer
4. Deploy WAR file to Tomcat
5. Configure Memcached and RabbitMQ
6. Restore database
7. Configure Security Groups
8. Attach Load Balancer
9. Test application endpoint

---

## 🧠 What I Learned

- Multi-tier architecture design
- Manual infrastructure provisioning
- Service-to-service communication
- Load balancing concepts
- Auto Scaling fundamentals
- Network security configuration
- Troubleshooting distributed systems
- Clear understanding of IaaS vs PaaS

<img width="1794" height="1020" alt="Screenshot 2026-01-30 170927" src="https://github.com/user-attachments/assets/ee574423-1be6-4b41-bed3-37391d39d810" />

