pipeline {

    agent any


    stages {


        stage('Clone Repo') {

            steps {

                git branch: 'main', url: 'https://github.com/AB772K/devops-lab-app.git'

            }

        }


        stage('Deploy to Kubernetes') {

            steps {

                sh 'kubectl apply -f deployment.yaml'

                sh 'kubectl get pods'

                sh 'kubectl get svc'

            }

        }


        stage('Verify') {

            steps {

                sh 'kubectl get all'

            }

        }

    }

}
