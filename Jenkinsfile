pipeline {
    agent any
    stages {
        stage('docker-compose up') {
            steps {
                sh 'python --version'
                sh 'cd ..'
                sh 'pwd'
                sh 'ls'
                sh 'docker ps'
                sh 'docker ps -la'
                sh 'cat docker-compose.yml'
                sh 'docker-compose up'
                sh 'docker-compose stop'

            }
        }

    }
}