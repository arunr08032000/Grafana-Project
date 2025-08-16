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
        stage('Tag image') {
            steps {
		sh 'sudo docker tag grafana/grafana-oss:10.4.19 arunr08032000/projects:grafana-server && sudo docker tag prom/prometheus:v2.52.0 arunr08032000/projects:prometheus-server'
	    }
	}
	stage('Push image to DockerHub') {
	    steps {
		sh 'sudo docker push arunr08032000/projects:grafana-project'
	    }
	}
    }
}
