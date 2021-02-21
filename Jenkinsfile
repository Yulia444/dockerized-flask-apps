pipeline {
    agent any
    stages {
        stage('docker-compose up') {
            steps {
                sh 'cat docker-compose.yml'
                sh 'docker-compose up -d'

            }
        }
        stage('stop running containers') {
            steps {
                sh 'docker-compose stop'
            }
        }

    }
}