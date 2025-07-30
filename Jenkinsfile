pipeline {
    agent any

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
                    bat 'make build'
                }
            }
        }

        stage('Unit Test') {
            steps {
                script {
                    // Run unit tests
                    bat 'make test'  // Modify this according to your test process
                }
            }
        }

        stage('Static Code Analysis') {
            steps {
                script {
                    // Run static code analysis
                    bat 'make lint'  // Modify this according to your static analysis tool
                }
            }
        }

        stage('Security Scan') {
            steps {
                script {
                    // Run security scans
                    bat 'make security-scan'  // Modify this according to your security scanning tool
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