pipeline {
    agent any
    
    tools {nodejs "node"}

    stages {
        stage('Build') {
            steps {
                sh 'cd hypertime-frontend && npm install && cd ..'
            }
        }
        stage('Build production file'){
            steps{
                sh 'cd hypertime-frontend && npm run build && cd ..'
            }
        }
        
        stage('Test') {
            steps {
                sh 'cd hypertime-frontend && npm run testecho && cd ..'
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}