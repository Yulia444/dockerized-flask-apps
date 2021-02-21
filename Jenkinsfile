pipeline {
    agent { 
        docker{
        image 'python:3.5.1'
        }
     }
    stages {
        stage('build') {
            steps {
                sh 'python --version'
            }
        }
        stage('docker-compose'){
            steps {
                sh 'docker-compose up'
            }
        }
    }
}