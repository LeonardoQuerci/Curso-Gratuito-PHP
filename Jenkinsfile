pipeline {
    agent any

    stages {
        stage('Build Docker') {
            steps {
                sh 'docker build -t site-social .'
            }
        }

        stage('Remover Container Antigo') {
            steps {
                sh 'docker rm -f site-social || true'
            }
        }

        stage('Subir Novo Container') {
            steps {
                sh 'docker run -d -p 8081:80 --name site-social site-social'
            }
        }

    }
}