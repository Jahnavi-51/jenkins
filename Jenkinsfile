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
                // Ensure Python is available, and show Python version
                bat '''
                    @echo off
                    python --version
                    if %ERRORLEVEL% neq 0 exit /b %ERRORLEVEL%
                '''
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

    post {
        failure {
            echo 'Pipeline failed.'
        }
        success {
            echo 'Pipeline executed successfully.'
        }
    }
}
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
