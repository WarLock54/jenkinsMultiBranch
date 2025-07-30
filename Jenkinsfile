pipeline {
    agent any
    environment {
        MAKE_PATH = "C:\\Program Files (x86)\\GnuWin32\\bin\\make.exe"
    }
    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/WarLock54/jenkinsMultiBranch.git', branch: 'main'
            }
        }

          stage('Build') {
            steps {
                bat "${env.MAKE_PATH} build"
            }
        }

        stage('Unit Test') {
            steps {
                bat "${env.MAKE_PATH} test"
            }
        }

        stage('Static Code Analysis') {
            steps {
                echo 'Running static analysis...'
                // add tools or scripts here
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Running security scan...'
                // add security tools here
            }
        }
    }

    post {
        always {
            cleanWs()  // Clean workspace after each build
        }
    }
}