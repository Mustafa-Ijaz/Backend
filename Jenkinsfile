pipeline {
  agent any
  environment {
    registryCredential = 'dockerhub'
   }
  stages {
    stage('Build') {
      steps {
          sh 'docker build -t mustafa75/test-image .'
          echo 'Build Sucessfull'
      }
     }
    stage('Test') {
      steps {
          sh 'docker container run -p 9090:8080 --name node -d mustafa75/test-image'
          sh 'curl -I http://localhost:9090'
          echo 'Testing Sucessfull'
      }
    }
    stage('Publish') {
      steps{
        script {
        docker.withRegistry( '', registryCredential ) {
        sh 'docker push mustafa75/test-image:latest'
          }
          echo 'Published Sucessfully'
        }
      }
    }
  }
}
