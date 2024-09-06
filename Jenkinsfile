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
        script {
            def emailResult = emailext(
                subject: "Pipeline Status: ${currentBuild.result}",
                body: "Pipeline execution completed. Status: ${currentBuild.result}",
                to: 'shrijithn2004@gmail.com',
                attachLog: true
            )
            echo "Email sending result: ${emailResult}"
        }
    }
}
