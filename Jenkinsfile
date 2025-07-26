pipeline {
    agent any
    stages {
        stage('Checkout code') {
            steps {
                checkout scm
            }
        }
        stage('Check Node.js and npm version') {
            steps {
                bat 'node -v'
                bat 'npm -v'
            }
        }
        stage('Install dependencies') {
            steps {
                bat 'npm install'
            }
        }
        stage('Start application') {
            steps {
                bat 'start /b npm start'
                bat 'ping 127.0.0.1 -n 6 > nul'
            }
        }
        stage('Run tests') {
            steps {
                bat 'npm test'
            }
        }
    }
} 