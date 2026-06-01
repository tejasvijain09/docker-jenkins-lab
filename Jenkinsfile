pipeline {

    agent any

    environment {
        IMAGE_NAME = "docker-jenkins-lab"
    }

    stages {

        stage('Checkout Code') {
            steps {
                git 'https://github.com/tejasvijain09/docker-jenkins-lab.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t %IMAGE_NAME% .'
            }
        }

        stage('Show Docker Images') {
            steps {
                bat 'docker images'
            }
        }
    }

    post {

        success {
            echo 'Docker image built successfully'
        }

        failure {
            echo 'Docker image build failed'
        }
    }
}
