pipeline {
    agent any

    stages {
        stage('Create network') {
            when {
              expression {
                return "!$(docker network ls | grep nginx-proxy)"
              }
            }
            steps {
                sh 'sudo docker network create nginx-proxy'
            }
        }

        stage('Spin up nginx') {
            steps {
                sh 'sudo docker-compose up -d'
            }
        }
    }
}