pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                echo 'Building the code using Maven'
            }
        }
        
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit tests with JUnit and integration tests with Selenium'
            }
        }
        
        stage('Code Analysis') {
            steps {
                echo 'Analyzing code with SonarQube'
            }
        }
        
        stage('Security Scan') {
            steps {
                echo 'Performing security scan with OWASP ZAP'
            }
        }
        
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to AWS EC2 staging server'
            }
        }
        
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging environment'
            }
        }
        
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to AWS EC2 production server'
            }
        }
    }
    post {
    always {
        emailext body: "Pipeline status: ${currentBuild.result}",
                 subject: "Pipeline Notification: ${currentBuild.fullDisplayName}",
                 to: 'shrijithn2004@gmail.com',
                 attachLog: true
    }
    }
}
