pipeline {
    agent any

    environment {
        DOCKERHUB_CREDENTIALS = credentials('docker-dockerhub')
    }

    stages {
        stage('Validate') {
            steps {
                sh '''
                sudo docker compose config --quiet && echo "OK" || echo "ERROR"
                '''
            }
        }

        stage('Deploy') {
            steps {
                sh 'sudo docker compose up -d'
            }
        }
    }
}
