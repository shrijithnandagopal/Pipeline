pipeline {
    agent any
    environment {
        LOG_FILE = 'pipeline.log'
        EMAIL_RECIPIENTS = 'mithunjet8@gmail.com'
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                echo 'Tool: Maven'
               
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
                echo 'Tool: JUnit'
         
            }
            post {
                success {
                    emailext(
                        to: "${EMAIL_RECIPIENTS}",
                        subject: "Unit and Integration Tests Successful",
                        body: "The unit and integration tests were successful.\nCheck Jenkins for more details.",
                        attachmentsPattern: "${LOG_FILE}"
                    )
                }
                failure {
                    emailext(
                        to: "${EMAIL_RECIPIENTS}",
                        subject: "Unit and Integration Tests Failed",
                        body: "The unit and integration tests failed.\nCheck Jenkins for more details.",
                        attachmentsPattern: "${LOG_FILE}"
                    )
                }
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Running code analysis...'
                echo 'Tool: SonarQube'
               
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Running security scan...'
                echo 'Tool: OWASP ZAP'
            }
            post {
                success {
                    emailext(
                        to: "${EMAIL_RECIPIENTS}",
                        subject: "Security Scan Successful",
                        body: "The security scan was successful.\nCheck Jenkins for more details.",
                        attachmentsPattern: "${LOG_FILE}"
                    )
                }
                failure {
                    emailext(
                        to: "${EMAIL_RECIPIENTS}",
                        subject: "Security Scan Failed",
                        body: "The security scan failed.\nCheck Jenkins for more details.",
                        attachmentsPattern: "${LOG_FILE}"
                    )
                }
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging...'
                echo 'Tool: AWS CLI'
             
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging...'
                echo 'Tool: Custom Test Suite'
               
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production...'
                echo 'Tool: AWS CLI'
               
            }
        }
    }
}
