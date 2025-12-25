 # CI/CD Pipeline Automation using Jenkins–Tomcat 



 📌 Project Overview
This project demonstrates **CI/CD pipeline automation using Jenkins** to build, test, and deploy a **Java web application** on **Apache Tomcat**.  
The pipeline uses **Maven** for build automation and runs on a **Linux environment**, simulating a real-world DevOps workflow.




🏗️ Architecture
Developer → GitHub

↓

Jenkins
(Build + Test)

↓

Maven
(WAR Package)

↓

Apache Tomcat
(Application Deploy)



 🛠️ Tools & Technologies Used
- Jenkins – CI/CD pipeline automation  
- Apache Maven – Build and dependency management  
- Apache Tomcat – Application server  
- Git & GitHub – Version control  
- Java 8 – Application runtime  
- Linux – Server environment  


 🔄 CI/CD Workflow
1. Developer pushes code to GitHub  
2. Jenkins pipeline is triggered automatically  
3. Jenkins checks out source code  
4. Maven compiles the code and runs unit tests  
5. WAR file is generated  
6. Jenkins deploys the WAR file to Apache Tomcat  
7. Application becomes accessible via browser  


📂 Project Structure

jenkins-tomcat-ci-cd/

├── README.md

├── Jenkinsfile

├── pom.xml

├── src/

├── docs
    ├──  Jenkins_Tomcat_CICD_Project.pptx

└── screenshots
     ├── jenkins-job.png
     ├── build-success.png
     ├── tomcat-app.png
    

⚙️ Jenkins Pipeline Stages

Checkout – Pull source code from GitHub

Build – Compile and package using Maven

Test – Execute unit tests

Deploy – Deploy WAR file to Apache Tomcat


📦 Build Command

To build the application manually:

mvn clean package


🚀 Deployment

After a successful build, the WAR file is deployed to:

$TOMCAT_HOME/webapps/


🌐 Application Access

Access the application using:

http://<server-ip>:8080/sampleapp


📸 Screenshots

Visual proof of the pipeline execution and deployment is available in the screenshots/ directory:

Jenkins job configuration.

Successful build output.

Application running on Tomcat.


📊 Project Documentation

Detailed project explanation and architecture diagrams are available here:

docs/Jenkins_Tomcat_CICD_Project.pptx                                           
