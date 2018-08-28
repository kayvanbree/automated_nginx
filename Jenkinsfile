pipeline {
    agent any

    stages {
        stage('Create network') {
            steps {
                sh 'docker network create nginx-proxy'
            }
        }

        stage('Spin up nginx') {
            steps {
                sh 'docker-compose up -d'
            }
        }
    }
}