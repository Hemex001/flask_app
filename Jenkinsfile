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
		sh 'sleep 10'
                sh 'docker-compose exec flask_app pytest'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker-compose up -d'
            }
        }
    }
}

