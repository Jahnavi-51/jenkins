pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Clone the GitHub repository and specify the branch (e.g., 'main')
                git branch: 'main', url: 'https://github.com/Jahnavi-51/jenkins.git'
            }
        }

        stage('Setup Python') {
            steps {
                bat '''
                    @echo off
                    python --version
                    if %ERRORLEVEL% neq 0 exit /b %ERRORLEVEL%
                '''
            }
        }

        stage('Run Python Script') {
            steps {
                bat '''
                    @echo off
                    python -u script.py
                    if %ERRORLEVEL% neq 0 exit /b %ERRORLEVEL%
                '''
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed.'
        }
        success {
            echo 'Pipeline executed successfully.'
        }
    }
}
