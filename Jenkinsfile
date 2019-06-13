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
                sh 'cd hypertime-frontend && npm run test && cd ..'
            }
        }
        stage('Test echo') {
            steps {
                sh "echo \"${env.WORKSPACE}\"/hypertime-frontend/build"
            }
        }
        stage('devloy') {
            steps {
               sh 'az storage blob upload-batch -s  /var/lib/jenkins/workspace/Hypertime_jenkinsfile/hypertime-frontend/build -d '$web' --connection-string=DefaultEndpointsProtocol=https;AccountName=hypertime;AccountKey=/hKquqMB4jLoma30s9HdVXJhiCIf++3loLZQe2nz0RPjPXiMs7xd8B96vFGsvr8lPVpMMVyp7rbBXBQ9+R+XYA==;EndpointSuffix=core.windows.net'
            }
        }
        
    }
}