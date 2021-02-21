pipeline {
    environment{
        dockerHubCredentials = "docker-hub-credentials"
        dockerHubUsername = "juliaolkhovyk"
        dockerImageTag = "1.0.0"
        imageName1 = "$dockerHubUsername/stepik-teachers:$dockerImageTag"
        imageName2 = "$dockerHubUsername/food-delivery:$dockerImageTag"
    }
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
        stage('build images'){
            steps {
                script {
                    dockerImage1 = docker.build(imageName1, 'stepik_teachers_master/.')
                    dockerImage2 = docker.build(imageName2, 'flask-food-delivery-master/.')
                }
            }
            
        }
        stage('deploy images'){
            steps{
                script {
                    docker.withRegistry('', dockerHubCredentials) {
                        dockerImage1.push()
                        dockerImage2.push()
                    }
                }
            }
        }
        stage('remove images'){
            steps{
                sh "docker rmi $imageName1 $imageName2"
            }
        }

    }
}