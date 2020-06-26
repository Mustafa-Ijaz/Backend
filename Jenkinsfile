pipeline {
  agent any
  environment {
    registryCredential = 'dockerhub'
   }
  stages {
    stage('Build') {
      steps {
          sh 'docker build -t mustafa75/Backend .'
          
      }
     }
    stage('Test') {
      steps {
          sh 'docker container run -p 9090:8080 --name node -d mustafa75/Backend'
          sh 'curl -I http://localhost:9090'
          
      }
    }
    stage('Publish') {
      steps{
        script {
        docker.withRegistry( '', registryCredential ) {
        sh 'docker push mustafa75/Backend:latest'
          }
        }
      }
    }
  }
}
