pipeline {
    agent any
    stages {
        stage('Checkout code') {
            steps {
                checkout scm
            }
        }
        stage('Set up Node.js') {
            steps {
                // This requires the Jenkins NodeJS plugin and a configured NodeJS installation named 'NodeJS'
                tool name: 'NodeJS', type: 'jenkins.plugins.nodejs.tools.NodeJSInstallation'
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
                // Optionally, wait a few seconds for the app to start
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