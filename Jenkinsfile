pipeline {
    agent any
    environment {
      DOCKERHUB_CREDENTIALS = credentials('docker-dockerhub')
    }
    stages {
        stage('Deploy') {
            steps {
            sh 'sudo docker compose config --quiet && printf "OK\n" || printf "ERROR\n"'
      }
    }
        stage('Deploy') {
            steps {
	    sh 'sudo docker-compose up -d'
      }
    }
  }
}
