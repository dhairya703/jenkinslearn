pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t my-app:latest .'
            }
        }

        stage('Run Container') {
            steps {
                bat 'docker run my-app:latest'
            }
        }
    }
}
