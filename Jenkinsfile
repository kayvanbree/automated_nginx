pipeline {
    agent any

    environment {
        NGINX_FOLDER = '/srv/www/nginx-proxy/'
    }

    stages {
        stage('Create network') {
            steps {
                sh 'docker network create nginx-proxy || true'
            }
        }

        stage('Prepare server') {
            steps {
                sh 'cp nginx.tmpl ${NGINX_FOLDER}'
            }
        }

        stage('Spin up nginx') {
            steps {
                sh 'docker-compose up -d'
            }
        }
    }
}