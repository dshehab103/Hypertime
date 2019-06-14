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
        stage('deploy') {
            steps {
               sh 'az storage blob upload-batch -s  /var/lib/jenkins/workspace/Hypertime_master/hypertime-frontend/build -d $web --connection-string=DefaultEndpointsProtocol=https;AccountName=delwar12;AccountKey=gCddC/TKtyd2dkt+bNWFHmb2tX6rpB0TlKiUP0zQNFercNkM32pU6p5zmk3t/RUzw9TdUqHLrq/Ic8JkKVj5MA==;EndpointSuffix=core.windows.net
            }
        }
        
    }
}