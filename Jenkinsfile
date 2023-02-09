pipeline {
    agent any
    stages {
        stage('Git clone') {
            steps{
                git branch: 'master', url: 'https://github.com/julianooen/Calculator-go-kubernetes.git'
            }
        }
        stage('minikube') {
            steps {
                sh 'minikube start'
            }
        }
        stage('deployment and service') {
            steps {
                sh "kubectl apply -f go-deployment.yaml && kubectl apply -f go-service.yaml"
            }
        }
	stage('service up'){
            steps {
                sh 'minikube service gocalculator'
            }
        }
    }
} 