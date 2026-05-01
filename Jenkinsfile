pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-app:latest .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run --rm my-app:latest'
            }
        }
    }
}
