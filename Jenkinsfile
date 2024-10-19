pipeline {   
    agent any

    stages {
        stage('Deploy To Kubernetes') {
            steps {
                withKubeConfig(caCertificate: '', clusterName: '', contextName: '', credentialsId: 'k8-token', namespace: '', restrictKubeConfigAccess: false, serverUrl: '')  {
                    sh "kubectl apply -f deployment-service.yml"
                    
                }
            }
        }
        
        stage('verify Deployment') {
            steps {
                withKubeConfig(caCertificate: '', clusterName: '', contextName: '', credentialsId: 'k8-token', namespace: '', restrictKubeConfigAccess: false, serverUrl: '')  {
                    sh "kubectl get svc"
                }
            }
        }
    }
}
