pipeline {
    agent any
    stages {
        stage('docker-compose up') {
            steps {
                sh 'cat docker-compose.yml'
                sh 'docker-compose up'

            }
        }
        stage('stop running containers') {
            steps {
                sh 'docker stop job_main_stepik_teachers_1'
                sh 'docker stop job_main_flask-food-delivery_1'
                sh 'docker stop job_main_db_1'
            }
        }

    }
}