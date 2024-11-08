pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'docker-compose down'
                sh 'docker-compose up --build -d'
            }
        }
        stage('Test') {
            steps {
                sh 'docker-compose exec web pytest'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker-compose up -d'
            }
        }
    }
}

