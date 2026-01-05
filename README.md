# 🚀 CI/CD Pipeline Automation Using Jenkins and Apache Tomcat (Single Server)

## 📌 Project Overview
This project demonstrates a **CI/CD pipeline** for deploying a **Java web application** using **Jenkins and Apache Tomcat** on a **single Linux server**.

The pipeline automates:
- Pulling source code from Git
- Building the application using Maven
- Deploying the WAR file to Apache Tomcat

This setup represents a **classic and widely used CI/CD architecture**, commonly found in **enterprise environments**.

---

## 🏗️ Architecture (Single Server)
```text
Developer → GitHub
              ↓
          Jenkins
        (Build + Package)
              ↓
            Maven
          (WAR File)
              ↓
        Apache Tomcat
        (Application Server)
              ↓
        Web Application
```
🛠️ Tools & Technologies Used
- Linux (Ubuntu)

- Java 11

- Git

- Apache Maven

- Jenkins

- Apache Tomcat

📂 Project Structure
```text
jenkins-tomcat-ci-cd/
├── README.md
├── Jenkinsfile (optional)
├── pom.xml
├── src/
│   └── main/
│       └── webapp/
└── screenshots/
```
🔧 Prerequisites
- One Linux server (Ubuntu 20.04 / 22.04)

- User with sudo access

- Internet connectivity

🔹 Step-by-Step Setup (Linux Commands)
STEP 1️⃣ Update System
```text
sudo apt update -y
sudo apt upgrade -y
```
STEP 2️⃣ Install Java
```text
sudo apt install openjdk-11-jdk -y
java -version
```
STEP 3️⃣ Install Jenkins
```text
curl -fsSL https://pkg.jenkins.io/debian/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null

echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null

sudo apt update -y
sudo apt install jenkins -y
```
Start Jenkins:

```text
sudo systemctl start jenkins
sudo systemctl enable jenkins
```
Access Jenkins:

```text
http://SERVER_IP:8080
```
Get admin password:

```text
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```
STEP 4️⃣ Install Maven
```text
sudo apt install maven -y
mvn -version
```
STEP 5️⃣ Install Git
```text
sudo apt install git -y
git --version
```
STEP 6️⃣ Install Apache Tomcat
```text
cd /opt
sudo wget https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.87/bin/apache-tomcat-9.0.87.tar.gz
sudo tar -xvf apache-tomcat-9.0.87.tar.gz
sudo mv apache-tomcat-9.0.87 tomcat
```
Set permissions:

```text
sudo chmod -R 775 /opt/tomcat
sudo chown -R $USER:$USER /opt/tomcat
```
Start Tomcat:

```text
/opt/tomcat/bin/startup.sh
```
Access Tomcat:

```text
http://SERVER_IP:8080
```
⚙️ Jenkins Job Configuration
Job Type
- Freestyle Project

Source Code Management
- Git

- Repository URL: https://github.com/your-repo/sampleapp.git

Build Step – Maven
```text
mvn clean package
```
WAR file created at:

```text
target/*.war
```
Deploy WAR to Tomcat
```text
cp target/*.war /opt/tomcat/webapps/
```
Restart Tomcat:

```text
/opt/tomcat/bin/shutdown.sh
/opt/tomcat/bin/startup.sh
```
🌐 Application Access
```text
http://SERVER_IP:8080/<application-name>
```
🔄 CI/CD Workflow Summary
- Developer pushes code to GitHub

- Jenkins pulls the source code

- Maven builds the WAR file

- Jenkins deploys WAR to Tomcat

- Application is live

📌 Key DevOps Concepts Demonstrated
- CI/CD Pipeline Automation

- Jenkins Build Automation

- Maven Dependency Management

- Tomcat Application Deployment

- Linux Server Administration

🧠 Interview Explanation (Short)
This project implements a CI/CD pipeline using Jenkins to automate the build and deployment of a Java web application. Maven handles packaging, and Apache Tomcat hosts the application on a Linux server.

✅ Future Enhancements
- Jenkins Pipeline (Jenkinsfile)

- GitHub Webhook integration

- Automated testing stage

- Multi-server deployment

- Docker-based Tomcat migration

📎 Author
Vignesh Reddy
DevOps | Jenkins | CI/CD | Apache Tomcat
