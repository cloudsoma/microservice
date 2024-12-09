  pipeline {
    agent any

    stages {
        stage('Kubernetes Deploy') {
            steps {
                 withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-2', contextName: '', credentialsId: '', namespace: 'webapps', serverUrl: 'https://1B9E955091BBAA0BC50D13FCA804D66E.gr7.ap-south-1.eks.amazonaws.com']]) {
                    sh "kubectl apply -f deployment-service.yml"
                }
            }
        }
     stage('Kubernetes verify') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-2', contextName: '', credentialsId: '', namespace: 'webapps', serverUrl: 'https://1B9E955091BBAA0BC50D13FCA804D66E.gr7.ap-south-1.eks.amazonaws.com']]) {
                   sh "kubectl get svc -n webapps"
                } 
            }
        }
    }
} 

