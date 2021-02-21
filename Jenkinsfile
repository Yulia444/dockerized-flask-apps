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
                sh 'ls'
                
            }
        }

    }
}