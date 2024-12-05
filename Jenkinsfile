 pipeline {
    agent any

    stages {
        stage('Kubernetes Deploy') {
            steps {
                withKubeConfig(caCertificate: '', clusterName: 'EKS-1', contextName: '', credentialsId: 'token', namespace: 'webapps', restrictKubeConfigAccess: false, serverUrl: 'https://408EB9C882036A993259678F337D98AA.yl4.ap-south-1.eks.amazonaws.com') {
                    sh "kubectl apply -f deployment-service.yml"
                }
            }
        }
    }
}

