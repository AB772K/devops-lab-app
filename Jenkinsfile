
pipeline {

    agent any


    environment {

        KUBECONFIG = '/var/jenkins_home/.kube/config'

    }


    stages {


        stage('Checkout') {

            steps {

                git branch: 'main', url: 'https://github.com/AB772K/devops-lab-app.git'

            }

        }


        stage('Build Docker Image') {

            steps {

                sh 'docker build -t flask-app .'

            }

        }


        stage('Deploy to Kubernetes') {

            steps {

                sh 'kubectl apply -f deployment.yaml'

            }

        }


        stage('Verify Deployment') {

            steps {

                sh 'kubectl get pods'

                sh 'kubectl get svc'

            }

        }

    }


    post {

        success {

            echo 'Pipeline SUCCESS'

        }

        failure {

            echo 'Pipeline FAILED'

        }

    }

}
