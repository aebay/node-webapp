pipeline {
    agent {  
        label 'linux-node'  
    }  
    stages {
        stage('Checkout') {  
            steps {  
                git credentialsId: 'aebay', url: 'https://github.com/[aebay]/node-webapp.git', branch: 'main'
            }  
        }  
        stage('Build Docker Image') {
            steps {  
                script {  
                    docker.build('node-webapp:latest')
                }
            }  
        }  
        stage('Run Docker Container') {
            steps {  
                script {  
                    docker.image('node-webapp:latest').run('-d -p 3000:3000')
                }  
            }  
        }
    }  
}

