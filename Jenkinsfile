pipeline {
    environment {
        registry = "mahmoudteha/capstone"
        registryCredential = 'dockerhub'
        dockerImage = ''
    }
    agent any
    stages {
        stage('Lint HTML') {
            steps {
                sh 'echo Linting HTML'
                sh 'tidy -q -e *.html'
            }
        }
        stage('Building image') {
            steps{
                script {
                    dockerImage = docker.build registry + ":$BUILD_NUMBER"
                }
            }
        }
        stage('Deploy Image') {
            steps{
                script {
                    docker.withRegistry( '', registryCredential ) {
                        dockerImage.push()
                    }
                }
            }
        }
        stage('Deploy Kubernetes') {
            steps{
                sh 'kubectl apply -f kubernetes.yml'
                sh 'kubectl get nodes'
                sh 'kubectl get deployments'
                sh 'kubectl get pod -o wide'
            }
        }
    }
}
