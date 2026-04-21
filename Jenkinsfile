pipeline {

    agent any


    stages {


        stage('Clone Repository') {

            steps {

                git branch: 'main', url: 'https://github.com/AB772K/devops-lab-app.git'

            }

        }


        stage('Build Docker Image') {

            steps {

                sh 'docker build -t flask-app .'

            }

        }


        stage('Run Container') {

            steps {

                sh '''

                    docker stop flask-app || true

                    docker rm flask-app || true

                    docker run -d -p 5000:5000 --name flask-app flask-app

                '''

            }

        }


        stage('Verify') {

            steps {

                sh 'docker ps'

            }

        }

    }

}
