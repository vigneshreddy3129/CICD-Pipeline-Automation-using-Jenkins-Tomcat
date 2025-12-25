pipeline {
    agent any

    tools {
        maven 'Maven'
        jdk 'Java-11'
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/vigneshreddy3129/CICD-Pipeline-Automation-using-Jenkins-Tomcat.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Deploy to Tomcat') {
            steps {
                sh '''
                cp target/sampleapp.war /opt/tomcat/webapps/
                '''
            }
        }
    }
}
