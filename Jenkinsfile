pipeline {
    agent any

    environment {
        //AWS_REGION = 'us-west-2'
        // Add other necessary environment variables here
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from the repository
                checkout scm
            }
        }

        stage('Build') {
            steps {
                script {
                    // Build the application
                    sh 'make build'  // Modify this according to your build process
                }
            }
        }

        stage('Unit Test') {
            steps {
                script {
                    // Run unit tests
                    sh 'make test'  // Modify this according to your test process
                }
            }
        }

        stage('Static Code Analysis') {
            steps {
                script {
                    // Run static code analysis
                    sh 'make lint'  // Modify this according to your static analysis tool
                }
            }
        }

        stage('Security Scan') {
            steps {
                script {
                    // Run security scans
                    sh 'make security-scan'  // Modify this according to your security scanning tool
                }
            }
        }
    }

    post {
        always {
            cleanWs()  // Clean workspace after each build
        }
    }
}