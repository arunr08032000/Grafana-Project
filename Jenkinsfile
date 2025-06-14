pipeline {
   agent any
   environment {
      DOCKERHUB_CREDENTIALS = credentials('docker-dockerhub')
   }
   stages {
      stage('Test')
         steps {
            sh 'sudo docker-compose up -d'
       }
   }
}
