pipeline {
    agent any
    stages {
        stage('Free port 8888') {
            steps {
                bat 'for /f "tokens=5" %%a in ("netstat -aon ^| findstr :8888 ^| findstr LISTENING") do taskkill /F /PID %%a'
            }
        }
        stage('Install dependencies') {
            steps {
                bat 'npm install'
            }
        }
        stage('Run tests') {
            steps {
                bat 'npm test'
            }
        }
    }
} 