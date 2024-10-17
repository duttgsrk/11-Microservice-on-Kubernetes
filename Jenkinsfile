pipeline {      
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                   withDockerRegistry(credentialsId: 'docker-cred', toolName: 'docker', url: 'https://hub.docker.com/repositories/dutt1')  {
                        sh "docker build -t dutt1/adservice:latest ."
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred', toolName: 'docker', url: 'https://hub.docker.com') {
                        sh "docker push dutt1/adservice:latest "
                    }
                }
            }
        }
    }
}
