pipeline {

    agent any


    environment {

        KUBECONFIG = '/var/jenkins_home/.kube/config'

    }


    stages {

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

                sh 'kubectl get pods'

                sh 'kubectl get svc'

            }

        }

    }

}
