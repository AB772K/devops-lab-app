pipeline {

    agent any


    stages {


        stage('Clone Repo') {

            steps {

                git branch: 'main', url: 'https://github.com/AB772K/devops-lab-app.git'

            }

        }


        stage('Deploy to Kubernetes (VM)') {

            steps {

                sh '''

                ssh -o StrictHostKeyChecking=no ab772k@localhost "

                    kubectl apply -f ~/devops-lab-app/devops-lab-app/deployment.yaml &&

                    kubectl get pods &&

                    kubectl get svc

                "

                '''

            }

        }


        stage('Verify') {

            steps {

                sh 'echo Deployment triggered successfully'

            }

        }

    }

}
