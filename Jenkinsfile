pipeline {
    agent any

    stages {
        stage('Create network') {
            steps {
                sh 'sudo docker network create nginx-proxy || true'
            }
        }

        stage('Spin up nginx') {
            steps {
                sh 'sudo docker-compose up -d'
            }
        }
    }
}