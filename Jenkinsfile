pipeline {
    environment{
        dockerHubCredentials = "docker-hub-credentials"
        dockerHubUsername = "juliaolkhovyk"
        dockerImageTag = "latest"
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
                sh 'cd stepik_teachers_master'
                script {
                    dockerImage1 = docker.build imageName1
                }
                sh 'cd ..'
                sh 'cd flask-food-delivery-master'
                script {
                    dockerImage2 = docker.build imageName2
                }
                sh 'cd ..'
            }
            
        }
        stage('deploy images'){
            steps{
                docker.withRegistry('', dockerHub) {
                    dockerImage1.push(imageName1)
                    dockerImage2.push(imageName2)
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