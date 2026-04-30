pipeline {
    agent any
environment {
    API_KEY = credentials('my-api-key')
}
    stages {

        stage('Install Dependencies') {
            steps {
                bat 'pip install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                bat 'pytest'
            }
        }

        stage('Run App') {
            steps {
                bat 'python app.py'
            }
        }
        stage('Check Env') {
    steps {
        bat 'echo %ENV%'
    }
}

        stage('Archive Artifacts') {
            steps {
                archiveArtifacts artifacts: '*.py', fingerprint: true
            }
        }
    }
}
