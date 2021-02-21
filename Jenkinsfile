pipeline {
    agent { 
        docker {
        image 'python:3.5.1'
        }
     }
    stages {
        stage('build') {
            steps {
                sh 'python --version'
                sh 'pwd'
                sh 'ls'
                sh 'cd ..'
                sh 'pwd'
                sh 'ls'
                sh 'cat docker-compose.yml'
                sh 'docker-compose up'

            }
        }

    }
}