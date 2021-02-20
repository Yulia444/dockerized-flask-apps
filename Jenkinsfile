pipeline {
    agent any
    stages{
        stage('Setting the variables values') {
            steps {
                sh '''
                    docker-compose up
                '''
            }
        }
    }
}