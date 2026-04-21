pipeline {

    agent any


    stages {

        stage('Checkout') {

            steps {

                git 'https://github.com/AB772K/devops-lab-app.git'

            }

        }


        stage('Build') {

            steps {

                sh 'docker build -t flask-app .'

            }

        }


        stage('Deploy') {

            steps {

                sh 'kubectl apply -f deployment.yaml'

            }

        }


        stage('Verify') {

            steps {

                sh 'kubectl get pods && kubectl get svc'

            }

        }

    }

}
