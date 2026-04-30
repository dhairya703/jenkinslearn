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
        bat 'echo %API_KEY%'
    }
}
           stage('Use Secret') {
            steps {
                withCredentials([string(credentialsId: 'my-api-key', variable: 'API_KEY')]) {
                    bat 'echo %API_KEY%'
                }
            }
        }
    }

        stage('Archive Artifacts') {
            steps {
                archiveArtifacts artifacts: '*.py', fingerprint: true
            }
        }
    }
}
