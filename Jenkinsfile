pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t gobikaka/trend-app:latest .'
            }
        }

        stage('Push Docker Image') {
            steps {
                sh 'docker push gobikaka/trend-app:latest'
            }
        }

        stage('Deploy to EKS') {
            steps {
                sh 'kubectl apply -f deployment.yaml'
                sh 'kubectl apply -f service.yaml'
            }
        }
    }
}
