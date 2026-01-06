pipeline {
    agent any

    environment {
        IMAGE_NAME = "akshatha28/mywebsite:latest"
    }

    stages {

        stage('Checkout Code') {
            steps {
                checkout scm
            }
        }

        stage('Docker Login') {
            steps {
                withCredentials([usernamePassword(
                    credentialsId: 'dockerhub-creds',
                    usernameVariable: 'DOCKER_USER',
                    passwordVariable: 'DOCKER_PASS'
                )]) {
                    sh 'echo $DOCKER_PASS | docker login -u $DOCKER_USER --password-stdin'
                }
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t akshatha28/mywebsite:latest .'
            }
        }

        stage('Push Docker Image') {
            steps {
                sh 'docker push akshatha28/mywebsite:latest'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                withCredentials([file(credentialsId: 'kubeconfig', variable: 'KUBECONFIG_FILE')]) {
                    sh '''
                        mkdir -p ~/.kube
                        cp $KUBECONFIG_FILE ~/.kube/config
                        chmod 600 ~/.kube/config

                        kubectl apply -f deployment.yaml
                        kubectl apply -f service.yaml
                        kubectl get pods
                        kubectl get svc
                    '''
                }
            }
        }
    }

    post {
        success {
            echo "✅ Capstone Project 2 deployed successfully"
        }
        failure {
            echo "❌ Pipeline failed"
        }
    }
}
