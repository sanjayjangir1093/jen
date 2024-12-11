pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/sanjayjangir1093/jen.git'
            }
        }
        stage('Build') {
            steps {
                sh 'npm install'
                sh 'docker build -t nodejs-app .'
            }
        }
        stage('Deploy to Kubernetes') {
            steps {
                script {
                    sh 'kubectl apply -f k8s/deployment.yaml'
                }
            }
        }
    }
}
