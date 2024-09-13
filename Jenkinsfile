pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Clone the GitHub repository
                git 'https://github.com/Jahnavi-51/jenkins.git'
            }
        }
       
        stage('Setup Python') {
            steps {
                // Ensure Python is available
                bat 'python --version'
            }
        }
       
        stage('Run Python Script') {
            steps {
                // Run the Python script
                bat '''
                    @echo off
                    python -u script.py
                    if %ERRORLEVEL% neq 0 exit /b %ERRORLEVEL%
                    '''
            }
        }
    }

   
}
