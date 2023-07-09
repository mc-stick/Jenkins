pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'echo "Building Docker images"'
                sh 'docker-compose build'
            }
        }
        stage('Test') {
            steps {
                sh 'echo "Running tests"'
                sh 'docker-compose run --rm app pytest'
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo "Deploying services"'
                sh 'docker-compose up -d'
            }
            
        }
    }
}
