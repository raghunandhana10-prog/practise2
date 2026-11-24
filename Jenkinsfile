pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Getting code from GitHub'
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                echo 'Building Docker Image'

                bat 'docker build -t jenkins-docker-demo .'
            }
        }

        stage('Run Docker Container') {
            steps {
                echo 'Running Docker Container'

                bat 'docker run --rm jenkins-docker-demo'
            }
        }
    }

    post {
        success {
            echo 'Jenkins and Docker Pipeline Successful!'
        }

        failure {
            echo 'Pipeline Failed!'
        }
    }
}