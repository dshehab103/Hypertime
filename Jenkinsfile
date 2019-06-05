pipeline {
    agent any
    
    tools {nodejs "node"}

    stages {
        stage('Build') {
            steps {
                bat 'cd hypertime-frontend && npm install && cd ..'
            }
        }
        stage('Build production file'){
            steps{
                bat 'cd hypertime-frontend && npm run build && cd..'
            }
        }
        
        stage('Test') {
            steps {
                bat 'cd hypertime-frontend && npm run testecho && cd..'
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}