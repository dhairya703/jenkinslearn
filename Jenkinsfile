pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                echo 'Cloning happens automatically in pipeline job'
            }
        }

        stage('Build') {
            steps {
                bat 'python app.py'
            }
        }
    }
}
