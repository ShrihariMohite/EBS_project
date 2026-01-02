# EBS_project
🏥 Insured – Health Insurance Claim Management System

A web-based Health Insurance Claim Management System built using Python Django and deployed on AWS Elastic Beanstalk, with RDS MySQL as the backend database.

This project allows users to submit insurance claims online and stores them securely in a cloud-hosted database.

🚀 Live Features

Submit health insurance claim

Store claims in AWS RDS (MySQL)

Hosted on AWS Elastic Beanstalk

Integrated EC2 connectivity

Secure & scalable cloud deployment

🧰 Tech Stack
Layer	Technology
Backend	Python, Django
Frontend	HTML, CSS
Database	MySQL (AWS RDS)
Cloud	AWS Elastic Beanstalk, EC2, RDS
Web Server	Nginx
Version Control	Git & GitHub
📂 Project Structure
insured/
│
├── .ebextensions/
│   └── django.config
├── static/
├── insured/
│   └── application.py
├── requirements.txt
├── insured.sql
├── nginx.conf
└── manage.py

🧑‍💻 How to Run Locally
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver

☁️ AWS Deployment Steps
1️⃣ Create RDS Database

Engine: MySQL

Tier: Free Tier

DB Name: insured

Enable Backup

Public Access: No

Save endpoint, username, password

2️⃣ Create Database Table
CREATE DATABASE IF NOT EXISTS insured;
USE insured;

CREATE TABLE IF NOT EXISTS claims (
  id INT AUTO_INCREMENT PRIMARY KEY,
  policy_id VARCHAR(255) NOT NULL,
  name VARCHAR(255) NOT NULL,
  dob DATE NOT NULL,
  mobile VARCHAR(20) NOT NULL,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

3️⃣ Configure Django Database

In django.config / settings:

DB_HOST = '<RDS-ENDPOINT>'
DB_NAME = 'insured'
DB_USER = '<USERNAME>'
DB_PASSWORD = '<PASSWORD>'

4️⃣ Create Elastic Beanstalk Application

Platform: Python

Environment type: Single Instance

Instance role: Existing Service Role

Enable public IP

Allow EC2 traffic

Upload project zip

5️⃣ Connect EC2 to RDS
sudo yum install mariadb105 -y
mysql -h <endpoint> -P 3306 -u <user> -p

6️⃣ Deploy Application

Go to Elastic Beanstalk

Upload project ZIP

Deploy

Open application URL

🧪 Result

User submits claim via form

Data stored in RDS

Confirmation message:

Claim submitted successfully. Our executives will call you shortly!

📸 Screenshots

✔ Claim form
✔ AWS deployment
✔ Successful claim submission
✔ Database records in MySQL

🧹 Cleanup

After testing:

Delete Elastic Beanstalk environment

Delete RDS instance

Terminate EC2 instance


🧑‍🎓 Author

Shrihari Mohite
Cloud & Python Developer
AWS | Django | MySQL | DevOps
